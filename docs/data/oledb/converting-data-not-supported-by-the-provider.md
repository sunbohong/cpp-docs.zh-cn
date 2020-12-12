---
description: 了解更多相关信息：转换提供程序不支持的数据
title: 转换不受提供程序支持的数据
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: 9fb449247ff40118e89dbebee5f43a1208a1f181
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323361"
---
# <a name="converting-data-not-supported-by-the-provider"></a>转换不受提供程序支持的数据

当使用者请求提供程序不支持的数据类型时，调用的 OLE DB 提供程序模板代码 `IRowsetImpl::GetData` Msdadc.dll 转换数据类型。

如果实现的接口需要进行 `IRowsetChange` 数据转换，则可以调用 Msdaenum.dll 来执行转换。 `GetData`例如，在为 atldb.h 中定义的使用。

## <a name="see-also"></a>请参阅

[使用 OLE DB 提供程序模板](../../data/oledb/working-with-ole-db-provider-templates.md)
