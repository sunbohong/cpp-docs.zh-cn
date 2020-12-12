---
description: 了解更多：数据源对象接口
title: 数据源对象接口
ms.date: 10/24/2018
helpviewer_keywords:
- data source objects [C++], interfaces
- data source objects [C++]
- interfaces [C++], OLE DB
- interfaces [C++], list of
- OLE DB provider templates [C++], object interfaces
- OLE DB [C++], interfaces
ms.assetid: 929e100c-c08c-4b64-8437-d8d1357226f6
ms.openlocfilehash: ecc37ca4286e288939ccd15bdcd073379c27f7c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287614"
---
# <a name="data-source-object-interfaces"></a>数据源对象接口

下表显示了 OLE DB 为数据源对象定义的必需和可选接口。

|接口|必需？|由 OLE DB 模板实现？|
|---------------|---------------|--------------------------------------|
|`IDBCreateSession`|必需|是|
|`IDBInitialize`|必需|是|
|`IDBProperties`|必需|是|
|[IPersist](/windows/win32/api/objidl/nn-objidl-ipersist)|必需|是|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|可选|否|
|`IDBDataSourceAdmin`|可选|否|
|`IDBInfo`|可选|否|
|[IPersistFile](/windows/win32/api/objidl/nn-objidl-ipersistfile)|可选|否|
|`ISupportErrorInfo`|可选|否|

数据源对象 `IDBProperties` 通过继承实现、 `IDBInitialize` 和 `IDBCreateSession` 接口。 可以通过继承或不从这些实现类之一继承来选择支持其他功能。 如果希望支持 `IDBDataSourceAdmin` 接口，则必须从 `IDBDataSourceAdminImpl` 类继承。

## <a name="see-also"></a>请参阅

[OLE DB 提供程序模板体系结构](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
