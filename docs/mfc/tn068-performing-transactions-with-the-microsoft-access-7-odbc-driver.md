---
description: 了解详细信息： TN068：使用 Microsoft Access 7 ODBC 驱动程序执行事务
title: TN068：使用 Microsoft Access 7 ODBC 驱动程序执行事务
ms.date: 06/28/2018
f1_keywords:
- vc.data.odbc
helpviewer_keywords:
- TN068 [MFC]
- transactions [MFC], calling BeginTrans
- transactions [MFC], Microsoft Access
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
ms.openlocfilehash: ebc98a0fd2bea78c0159daa9a53a11a292482257
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214541"
---
# <a name="tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver"></a>TN068：使用 Microsoft Access 7 ODBC 驱动程序执行事务

> [!NOTE]
> 以下技术说明在首次包括在联机文档中后未更新。 因此，某些过程和主题可能已过时或不正确。 要获得最新信息，建议你在联机文档索引中搜索热点话题。

本说明介绍当使用 Microsoft ODBC 桌面驱动程序包版本3.0 中包含的 MFC ODBC 数据库类和 Microsoft Access 7.0 ODBC 驱动程序时，如何执行事务。

## <a name="overview"></a>概述

如果数据库应用程序执行事务，则必须谨慎地在 `CDatabase::BeginTrans` `CRecordset::Open` 应用程序中按正确的顺序调用和。 Microsoft Access 7.0 驱动程序使用 Microsoft Jet 数据库引擎，而 Jet 要求您的应用程序不会在具有打开的游标的任何数据库上开始事务。 对于 MFC ODBC 数据库类，打开的游标等同于打开的 `CRecordset` 对象。

如果在调用前打开记录集 `BeginTrans` ，则可能看不到任何错误消息。 但是，在调用后，你的应用程序的所有记录集更新都将变为永久 `CRecordset::Update` 的，并且不会通过调用回滚更新 `Rollback` 。 若要避免此问题，必须 `BeginTrans` 先调用，然后打开记录集。

MFC 检查驱动程序功能的游标提交和回滚行为。 类 `CDatabase` 提供两个成员函数 `GetCursorCommitBehavior` 和 `GetCursorRollbackBehavior` ，用于确定任何事务对打开的对象的影响 `CRecordset` 。 对于 Microsoft Access 7.0 ODBC 驱动程序，这些成员函数将返回， `SQL_CB_CLOSE` 因为 Access 驱动程序不支持游标保存。 因此，必须在 `CRecordset::Requery` `CommitTrans` 或操作后调用 `Rollback` 。

如果需要逐个执行多个事务，则不能在第一个 `Requery` 事务之后调用，然后再启动下一个事务。 在下一次调用之前，必须先关闭记录集 `BeginTrans` ，才能满足 Jet 的要求。 本技术说明介绍了两种处理此情况的方法：

- 每次或操作后关闭记录集 `CommitTrans` `Rollback` 。

- 使用 ODBC API 函数 `SQLFreeStmt` 。

## <a name="closing-the-recordset-after-each-committrans-or-rollback-operation"></a>每次 CommitTrans 或回滚操作后关闭记录集

在开始事务之前，请确保 recordset 对象已关闭。 调用后 `BeginTrans` ，调用记录集的 `Open` 成员函数。 调用或后立即关闭记录 `CommitTrans` 集 `Rollback` 。 请注意，重复打开和关闭记录集会降低应用程序的性能。

## <a name="using-sqlfreestmt"></a>使用 SQLFreeStmt

你还可以使用 ODBC API 函数在 `SQLFreeStmt` 结束事务后显式关闭游标。 若要启动另一个事务，请调用 `BeginTrans` 后跟 `CRecordset::Requery` 。 调用时 `SQLFreeStmt` ，必须将记录集的 HSTMT 指定为第一个参数，并 *SQL_CLOSE* 指定为第二个参数。 此方法比关闭和打开每个事务开始时的记录集快。 下面的代码演示如何实现此方法：

```cpp
CMyDatabase db;
db.Open("MYDATASOURCE");
CMyRecordset rs(&db);

// start transaction 1 and
// open the recordset
db.BeginTrans();
rs.Open();

// manipulate data

// end transaction 1
db.CommitTrans(); // or Rollback()

// close the cursor
::SQLFreeStmt(rs.m_hstmt, SQL_CLOSE);

// start transaction 2
db.BeginTrans();
// now get the result set
rs.Requery();

// manipulate data

// end transaction 2
db.CommitTrans();

rs.Close();
db.Close();
```

实现此方法的另一种方法是编写一个新函数， `RequeryWithBeginTrans` 在提交或回滚第一个事务后，可以调用该函数来启动下一个事务。 若要编写此类函数，请执行以下步骤：

1. 将的代码复制 `CRecordset::Requery( )` 到新函数。

2. 在调用后立即添加以下行 `SQLFreeStmt` ：

   `m_pDatabase->BeginTrans( );`

现在，可以在每对事务之间调用此函数：

```cpp
// start transaction 1 and
// open the recordset
db.BeginTrans();

rs.Open();

// manipulate data

// end transaction 1
db.CommitTrans();   // or Rollback()

// close the cursor, start new transaction,
// and get the result set
rs.RequeryWithBeginTrans();

// manipulate data

// end transaction 2
db.CommitTrans();   // or Rollback()
```

> [!NOTE]
> 如果需要更改事务之间 *m_strFilter* 或 *m_strSort* 的记录集成员变量，请不要使用此方法。 在这种情况下，应在每个或操作后关闭记录集 `CommitTrans` `Rollback` 。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
