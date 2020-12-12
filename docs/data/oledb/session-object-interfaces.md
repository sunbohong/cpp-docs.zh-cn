---
description: 了解更多：会话对象接口
title: 会话对象接口
ms.date: 11/19/2018
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
ms.openlocfilehash: dc4f5644258b0ced4c97a5cda6de1b69abb8c2f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286574"
---
# <a name="session-object-interfaces"></a>会话对象接口

下表显示了 OLE DB 为 session 对象定义的必需和可选接口。

|接口|必需？|由 OLE DB 模板实现？|
|---------------|---------------|--------------------------------------|
|[IGetDataSource](/previous-versions/windows/desktop/ms709721(v=vs.85))|必需|是|
|[IOpenRowset](/previous-versions/windows/desktop/ms716946(v=vs.85))|必需|是|
|[ISessionProperties](/previous-versions/windows/desktop/ms713721(v=vs.85))|必需|是|
|[IAlterIndex](/previous-versions/windows/desktop/ms714943(v=vs.85))|可选|否|
|[IAlterTable](/previous-versions/windows/desktop/ms719764(v=vs.85))|可选|否|
|[IBindResource](/previous-versions/windows/desktop/ms714936(v=vs.85))|可选|否|
|[ICreateRow](/previous-versions/windows/desktop/ms716832(v=vs.85))|可选|否|
|[IDBCreateCommand](/previous-versions/windows/desktop/ms711625(v=vs.85))|可选|是|
|[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85))|可选|是|
|[IIndexDefinition](/previous-versions/windows/desktop/ms711593(v=vs.85))|可选|否|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|可选|是|
|[ITableCreation](/previous-versions/windows/desktop/ms713639(v=vs.85))|可选|否|
|[ITableDefinition](/previous-versions/windows/desktop/ms714277(v=vs.85))|可选|否|
|[ITableDefinitionWithConstraints](/previous-versions/windows/desktop/ms720947(v=vs.85))|可选|否|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|可选|否|
|[ITransactionJoin](/previous-versions/windows/desktop/ms718071(v=vs.85))|可选|否|
|[ITransactionLocal](/previous-versions/windows/desktop/ms714893(v=vs.85))|可选|否|
|[ITransactionObject](/previous-versions/windows/desktop/ms713659(v=vs.85))|可选|否|

Session 对象创建行集对象。 如果提供程序支持命令，则该会话还将创建一个命令对象 (`CCommand` ，同时实现 OLE DB `TCommand`) 。 Command 对象实现接口， `ICommand` 并使用方法在 `ICommand::Execute` 行集上执行命令，如下图所示。

![提供程序概念图](../../data/oledb/media/vc4u551.gif "提供程序概念图")

## <a name="see-also"></a>请参阅

[OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
