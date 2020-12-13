---
description: 了解详细信息： ATL COM 对象的基础知识
title: ATL COM 对象的基本知识
ms.date: 11/19/2018
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
ms.openlocfilehash: 0a94d57701770b00eb2c2d5aed675b8cc19e9e58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152931"
---
# <a name="fundamentals-of-atl-com-objects"></a>ATL COM 对象的基本知识

下图描绘了用于定义 ATL COM 对象的类和接口之间的关系。

![ATL 结构](../atl/media/vc307y1.gif "ATL 结构")

> [!NOTE]
> 此关系图显示了 `CComObject` 从派生 `CYourClass` 而来 `CComAggObject` ，并将其 `CComPolyObject` `CYourClass` 作为成员变量包括在内。

有三种方法可以定义 ATL COM 对象。 标准选项是使用 `CComObject` 派生自的类 `CYourClass` 。 第二种方法是使用类创建聚合对象 `CComAggObject` 。 第三种方法是使用 `CComPolyObject` 类。 `CComPolyObject` 作为混合方法：它可以作为 `CComObject` 类或作为 `CComAggObject` 类，具体取决于它的第一次创建方式。 有关如何使用类的详细信息 `CComPolyObject` ，请参阅 [CComPolyObject 类](../atl/reference/ccompolyobject-class.md)。

使用标准 ATL COM 时，可以使用两个对象：外部对象和内部对象。 外部客户端通过外部对象中定义的包装函数访问内部对象的功能。 外部对象的类型为 `CComObject` 。

当使用聚合对象时，外部对象不会为内部对象的功能提供包装。 相反，外部对象提供由外部客户端直接访问的指针。 在此方案中，外部对象的类型为 `CComAggObject` 。 内部对象是外部对象的成员变量，它属于类型 `CYourClass` 。

由于客户端不必通过外部对象与内部对象进行交互，因此聚合对象通常更有效。 此外，外部对象不必知道聚合对象的功能，因为聚合对象的接口直接可供客户端使用。 但是，并不是所有的对象都可以聚合。 对于要聚合的对象，需要在设计时考虑聚合。

ATL 在两个阶段内实现 [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) ：

- [CComObject](../atl/reference/ccomobject-class.md)、 [CComAggObject](../atl/reference/ccomaggobject-class.md)或 [CComPolyObject](../atl/reference/ccompolyobject-class.md) 实现了这些 `IUnknown` 方法。

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) 或 [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) 管理的引用计数和外部指针 `IUnknown` 。

ATL COM 对象的其他方面由其他类处理：

- [CComCoClass](../atl/reference/ccomcoclass-class.md) 定义对象的默认类工厂和聚合模型。

- [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 提供 `IDispatch Interface` 对象上任何双重接口部分的默认实现。

- [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) 实现了 `ISupportErrorInfo` 接口，该接口可确保错误信息可以正确地在调用链中向上传播。

## <a name="in-this-section"></a>本节内容

[实现 CComObjectRootEx](../atl/implementing-ccomobjectrootex.md)<br/>
显示用于实现的示例 COM 映射条目 `CComObjectRootEx` 。

[实现 CComObject、CComAggObject 和 CComPolyObject](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)<br/>
讨论 **DECLARE_ \* _AGGREGATABLE** 宏如何影响、和的使用 `CComObject` `CComAggObject` `CComPolyObject` 。

[支持 IDispatch 和 IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md)<br/>
列出用于支持和接口的 ATL 实现类 `IDispatch` `IErrorInfo` 。

[支持 IDispEventImpl](../atl/supporting-idispeventimpl.md)<br/>
讨论为类实现连接点的步骤。

[更改默认类工厂和聚合模型](../atl/changing-the-default-class-factory-and-aggregation-model.md)<br/>
显示要用于更改默认类工厂和聚合模型的宏。

[创建聚合对象](../atl/creating-an-aggregated-object.md)<br/>
列出创建聚合对象的步骤。

## <a name="related-sections"></a>相关章节

[创建 ATL 项目](../atl/reference/creating-an-atl-project.md)<br/>
提供有关创建 ATL COM 对象的信息。

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
提供了关于如何使用 Active Template Library 进行编程的概念性主题的链接。

## <a name="see-also"></a>请参阅

[概念](../atl/active-template-library-atl-concepts.md)
