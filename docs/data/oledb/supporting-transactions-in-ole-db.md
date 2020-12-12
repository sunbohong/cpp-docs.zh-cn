---
description: 了解详细信息：支持中的事务 OLE DB
title: 在 OLE DB 中支持事务
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB consumer templates [C++], transaction support
- transactions [C++], OLE DB support for
- nested transactions [C++]
- OLE DB [C++], transaction support
- databases [C++], transactions
- distributed transactions [C++]
ms.assetid: 3d72e583-ad38-42ff-8f11-e2166d60a5a7
ms.openlocfilehash: f8d01a0d359a3d33fbe4b88877d8a4452f257c16
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272716"
---
# <a name="supporting-transactions-in-ole-db"></a>在 OLE DB 中支持事务

[事务](../../data/transactions-mfc-data-access.md)是一种对数据源的一系列更新进行分组或批处理的方式，这样，无论是已成功提交，同时提交，还是在任何一个的 (失败) 提交，整个事务都将回滚。 此过程可确保对数据源的结果进行完整性。

OLE DB 支持具有以下三种方法的事务：

- [ITransactionLocal：： StartTransaction](/previous-versions/windows/desktop/ms709786(v=vs.85))

- [ITransaction：： Commit](/previous-versions/windows/desktop/ms713008(v=vs.85))

- [ITransaction：： Abort](/previous-versions/windows/desktop/ms709833(v=vs.85))

## <a name="relationship-of-sessions-and-transactions"></a>会话和事务的关系

单个数据源对象可以创建一个或多个会话对象，每个对象都可以在给定时间在事务范围内或外部。

如果会话未输入事务，则会在每次调用方法时立即提交在该会话中完成的所有工作。  (这有时称为自动提交模式或隐式模式。 ) 

当会话进入某一事务时，该会话中在该会话中完成的所有工作都是该事务的一部分，并作为一个单元提交或中止。  (这有时称为手动提交模式。 ) 

事务支持特定于提供程序。 如果你使用的提供程序支持事务，则支持和的会话 `ITransaction` 对象 `ITransactionLocal` 可以输入非嵌套) 事务 (。 OLE DB Templates 类 [CSession](../../data/oledb/csession-class.md) 支持这些接口，是实现 Visual C++ 中的事务支持的建议方法。

## <a name="starting-and-ending-the-transaction"></a>开始和结束事务

在 `StartTransaction` `Commit` `Abort` 使用者的行集对象中调用、和方法。

调用会 `ITransactionLocal::StartTransaction` 启动新的本地事务。 当您启动事务时，在提交事务之前，以后操作所要求的任何更改都不会应用于数据存储区。

调用 `ITransaction::Commit` 或 `ITransaction::Abort` 结束事务。 `Commit` 使事务范围内的所有更改都应用于数据存储区。 `Abort` 使事务范围内的所有更改都被取消，并且数据存储会处于事务启动前的状态。

## <a name="nested-transactions"></a>嵌套事务

当会话上已存在活动事务时，启动新的本地事务时，将发生 [嵌套事务](/previous-versions/windows/desktop/ms716985(v=vs.85)) 。 新事务作为嵌套事务在当前事务下启动。 如果提供程序不支持嵌套事务， `StartTransaction` 则在会话上已有活动事务时调用会返回 XACT_E_XTIONEXISTS。

## <a name="distributed-transactions"></a>分布式事务

分布式事务是更新分布式数据的事务;也就是说，多个网络计算机系统上的数据。 如果希望通过分布式系统支持事务，则应使用 .NET Framework 而不是 OLE DB 事务支持。

## <a name="see-also"></a>请参阅

[使用访问器](../../data/oledb/using-accessors.md)
