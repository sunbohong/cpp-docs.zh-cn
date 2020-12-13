---
description: 了解详细信息：实现 CComObjectRootEx
title: 实现 CComObjectRootEx
ms.date: 11/04/2016
helpviewer_keywords:
- CComObjectRoot class, implementing
- CComObjectRootEx class
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
ms.openlocfilehash: 235d10a8c390311230057da5dda11e5a8f093445
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152836"
---
# <a name="implementing-ccomobjectrootex"></a>实现 CComObjectRootEx

[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) 是必需的;所有 ATL 对象的继承中都必须有一个 `CComObjectRootEx` 或 [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) 的实例。 `CComObjectRootEx` 提供基于 COM 映射项的默认 `QueryInterface` 机制。

通过其 COM 映射，对象的接口将在客户端查询接口时向该客户端公开。 该查询通过 `CComObjectRootEx::InternalQueryInterface` 执行。 `InternalQueryInterface` 仅处理 COM 映射表中的接口。

可以将接口输入到 COM 映射表中，其中包含 [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) 宏或它的一个变量。 例如，以下代码输入可将接口 `IDispatch`、`IBeeper` 和 `ISupportErrorInfo` 输入到 COM 映射表：

[!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]

## <a name="see-also"></a>请参阅

[ATL COM 对象的基本知识](../atl/fundamentals-of-atl-com-objects.md)<br/>
[COM 映射宏](../atl/reference/com-map-macros.md)
