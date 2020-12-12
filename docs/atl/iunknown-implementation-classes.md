---
description: 了解有关： IUnknown 实现类的详细信息
title: 'IUnknown 实现类 (ATL) '
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
ms.openlocfilehash: a28bd14be86501fd6566b8038b73a51efcc1c18d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147649"
---
# <a name="iunknown-implementation-classes"></a>IUnknown 实现类

以下类实现 `IUnknown` 和相关方法：

- [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) 管理聚合对象和非聚合对象的引用计数。 允许您指定线程模型。

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) 管理聚合对象和非聚合对象的引用计数。 使用服务器的默认线程模型。

- [CComAggObject](../atl/reference/ccomaggobject-class.md) 实现 `IUnknown` 聚合对象。

- [CComObject](../atl/reference/ccomobject-class.md) 实现 `IUnknown` 非聚合对象。

- [CComPolyObject](../atl/reference/ccompolyobject-class.md) 实现 `IUnknown` 聚合对象和非聚合对象。 使用可 `CComPolyObject` 避免 `CComAggObject` `CComObject` 在模块中使用和。 单个 `CComPolyObject` 对象处理聚合和非聚合事例。

- [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) 实现 `IUnknown` 非聚合对象，而不修改模块锁计数。

- [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) 实现 `IUnknown` 对脱离接口的实现。

- [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) 实现 `IUnknown` "缓存的" 撕出接口。

- [CComContainedObject](../atl/reference/ccomcontainedobject-class.md) 实现 `IUnknown` 聚合或脱离接口的内部对象。

- [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) 管理模块上的引用计数，以确保不会删除您的对象。

- [CComObjectStack](../atl/reference/ccomobjectstack-class.md) 使用的框架实现创建一个临时 COM 对象 `IUnknown` 。

## <a name="related-articles"></a>相关文章

[ATL COM 对象的基本知识](../atl/fundamentals-of-atl-com-objects.md)

## <a name="see-also"></a>请参阅

[类概述](../atl/atl-class-overview.md)<br/>
[聚合和类工厂宏](../atl/reference/aggregation-and-class-factory-macros.md)<br/>
[COM 映射宏](../atl/reference/com-map-macros.md)<br/>
[COM 映射全局函数](../atl/reference/com-map-global-functions.md)
