---
description: 了解更多相关信息：实现 CComObject、CComAggObject 和 CComPolyObject
title: 实现 CComObject、CComAggObject 和 CComPolyObject
ms.date: 11/04/2016
helpviewer_keywords:
- CComPolyObject class, implementing
- CreateInstance method
- CComAggObject class
- CComObject class, implementing
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
ms.openlocfilehash: e0cc8a6b65ec9d85249cd47e2f43cf1bec2b8ce2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147766"
---
# <a name="implementing-ccomobject-ccomaggobject-and-ccompolyobject"></a>实现 CComObject、CComAggObject 和 CComPolyObject

模板类 [CComObject](../atl/reference/ccomobject-class.md)、 [CComAggObject](../atl/reference/ccomaggobject-class.md)和 [CComPolyObject](../atl/reference/ccompolyobject-class.md) 始终是继承链中派生程度最高的类。 负责处理中的所有方法 `IUnknown` ： `QueryInterface` 、 `AddRef` 和 `Release` 。 此外，将 `CComAggObject` `CComPolyObject` (用于聚合对象时) 提供内部未知所需的特殊引用计数和 `QueryInterface` 语义。

`CComObject`使用、 `CComAggObject` 或是否 `CComPolyObject` 使用取决于是否声明以下宏的 (或 none) ：

|宏|效果|
|-----------|------------|
|DECLARE_NOT_AGGREGATABLE|始终使用 `CComObject` 。|
|DECLARE_AGGREGATABLE|`CComAggObject`如果对象已聚合，则使用， `CComObject` 如果不是，则使用。 `CComCoClass` 包含此宏，因此，如果未在类中声明任何 DECLARE_ * _AGGREGATABLE 宏，这将是默认值。|
|DECLARE_ONLY_AGGREGATABLE|始终使用 `CComAggObject` 。 如果对象未聚合，则返回错误。|
|DECLARE_POLY_AGGREGATABLE|调用时，ATL 将 **创建 \<CYourClass> CComPolyObject** 的实例 `IClassFactory::CreateInstance` 。 在创建过程中，将检查外部 "未知" 的值。 如果为 NULL， `IUnknown` 则为非聚合对象实现。 如果外部未知值不为 NULL， `IUnknown` 则为聚合对象实现。|

使用和的优点 `CComAggObject` `CComObject` 是针对 `IUnknown` 要创建的对象类型优化了的实现。 例如，非聚合对象只需要引用计数，而聚合对象需要内部未知的引用计数和指向外部未知的指针。

使用的优点 `CComPolyObject` 是，你不必 `CComAggObject` 在模块中同时使用和 `CComObject` 来处理聚合和非聚合情况。 单个 `CComPolyObject` 对象处理两种情况。 这意味着在您的模块中只存在一个 vtable 副本和一个函数副本。 如果 vtable 很大，这可能会显著降低模块大小。 但是，如果你的 vtable 很小，则使用 `CComPolyObject` 可能会导致模块大小稍微大一些，因为它未针对聚合或非聚合对象进行优化，如 `CComAggObject` 和 `CComObject` 。

## <a name="see-also"></a>请参阅

[ATL COM 对象的基本知识](../atl/fundamentals-of-atl-com-objects.md)<br/>
[聚合和类工厂宏](../atl/reference/aggregation-and-class-factory-macros.md)
