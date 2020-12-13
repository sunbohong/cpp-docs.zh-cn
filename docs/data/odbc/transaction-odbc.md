---
description: '了解有关以下内容的详细信息： Transaction (ODBC) '
title: 事务 (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets [C++], updating
- transactions [C++], MFC ODBC classes
- ODBC [C++], transactions
- recordsets [C++], updating
- databases [C++], transactions
- recordsets [C++], transactions
- ODBC recordsets [C++], transactions
ms.assetid: a2ec0995-2029-45f2-8092-6efd6f2a77f4
ms.openlocfilehash: a7b769c37b58b34433939a18cb0dccf5fb4a798d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333868"
---
# <a name="transaction-odbc"></a>事务 (ODBC)

本主题适用于 MFC ODBC 类。

事务是一种对 [数据源](../../data/odbc/data-source-odbc.md) 的一系列更新进行分组或批处理的方式，这样一来，所有这些更新将立即提交，或者在回滚事务时提交任何内容。 如果不使用事务，将自动提交对数据源所做的更改，而不是按需提交。

> [!NOTE]
> 并非所有 ODBC 数据库驱动程序都支持事务。 调用 `CanTransact` [CDatabase](../../mfc/reference/cdatabase-class.md) 或 [CRecordset](../../mfc/reference/crecordset-class.md) 对象的成员函数，以确定驱动程序是否支持给定数据库的事务。 请注意，不 `CanTransact` 会告诉您数据源是否提供完全事务支持。 还必须调用 `CDatabase::GetCursorCommitBehavior` 和 `CDatabase::GetCursorRollbackBehavior` after `CommitTrans` ，并 `Rollback` 检查事务对打开的对象的影响 `CRecordset` 。

`AddNew`调用时，对 `Edit` 对象的和成员函数的调用 `CRecordset` 会立即影响数据源 `Update` 。 `Delete` 调用也会立即生效。 与此相反，您可以使用包含多个对、、和的调用的事务， `AddNew` `Edit` 这些调用 `Update` `Delete` 在您显式调用之前执行但不会提交 `CommitTrans` 。 通过建立事务，可以执行一系列这样的调用，同时保留回滚它们的能力。 如果某个关键资源不可用，或者某些其他条件阻止整个事务完成，则可以回滚该事务，而不是提交该事务。 在这种情况下，属于事务的任何更改都不会影响数据源。

> [!NOTE]
> 目前， `CRecordset` 如果已实现批量行提取，则类不支持对数据源进行更新。 这意味着不能对 `AddNew` 、 `Edit` 、或调用 `Delete` `Update` 。 但是，您可以编写自己的函数来执行更新，然后在给定事务中调用这些函数。 有关批量行提取的详细信息，请参阅 [记录集：批量提取记录 (ODBC) ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)。

> [!NOTE]
> 除了影响记录集外，事务还会影响你直接执行的 SQL 语句，只要你使用与你的对象关联的 ODBC **HDBC** `CDatabase` 或基于该 **HDBC** 的 odbc **HSTMT** 。

当你有多个必须同时更新的记录时，事务特别有用。 在这种情况下，你想要避免一半完成的事务，例如，如果在最后一次更新之前引发了异常，则可能会发生这种情况。 将此类更新分组到一个事务中，可使恢复 (从更改中) 回滚，并将记录返回到 pretransaction 状态。 例如，如果某一银行从帐户 A 传输到帐户 B 的资金，则从 A 和存款到 B 都必须成功地处理资金，否则整个事务必须失败。

在数据库类中，通过对象执行事务 `CDatabase` 。 `CDatabase`对象表示与数据源的连接，一个或多个与该对象关联的记录集 `CDatabase` 通过 recordset 成员函数对数据库的表进行操作。

> [!NOTE]
> 仅支持一级别的事务。 不能嵌套事务，也不能跨越多个数据库对象。

以下主题提供了有关如何执行事务的详细信息：

- [事务：在记录集中执行事务 (ODBC) ](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

- [事务：事务如何影响 ODBC (更新) ](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)

## <a name="see-also"></a>请参阅

[ODBC)  (打开数据库连接 ](../../data/odbc/open-database-connectivity-odbc.md)
