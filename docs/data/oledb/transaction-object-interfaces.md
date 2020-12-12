---
description: 了解详细信息：事务对象接口
title: 事务对象接口
ms.date: 10/24/2018
helpviewer_keywords:
- interfaces, OLE DB
- transaction object interfaces
- OLE DB, interfaces
- OLE DB providers, transaction support
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
ms.openlocfilehash: bc8eec6ca5a962e825eafa12255d8a47a8a463f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272638"
---
# <a name="transaction-object-interfaces"></a>事务对象接口

事务对象定义数据源的原子工作单元，并确定这些工作单元如何相互关联。 OLE DB 提供程序模板不直接支持此对象 (也就是说，你必须) 创建自己的对象。

下表显示了 OLE DB 为 transaction 对象定义的必需和可选接口。

|接口|必需？|由 OLE DB 模板实现？|
|---------------|---------------|--------------------------------------|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|必需|否|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|必需|否|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|可选|否|

## <a name="see-also"></a>另请参阅

[OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
