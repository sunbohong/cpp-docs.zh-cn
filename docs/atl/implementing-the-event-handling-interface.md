---
description: 了解有关以下内容的详细信息：实现事件处理接口
title: 实现事件处理接口
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, event handling
- event handling, ATL
- interfaces, event and event sink
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
ms.openlocfilehash: 109fbb1fbdd4f18d0eb4c295fbc08de2b7cc3a35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152758"
---
# <a name="implementing-the-event-handling-interface"></a>实现事件处理接口

ATL 可帮助您处理事件所需的全部三个元素：实现事件接口，通知事件源，并 unadvising 事件源。 需要执行的具体步骤取决于事件接口的类型和应用程序的性能要求。

使用 ATL 实现接口的最常见方法是：

- 直接从自定义接口派生。

- 从 [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 派生类型库中所述的双重接口。

- 从 [IDispEventImpl](../atl/reference/idispeventimpl-class.md) 派生类型库中所述的调度接口。

- 从 [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) 派生，而不是在类型库中描述的，或者当你希望在运行时不加载类型信息时提高效率。

如果要实现自定义或双重接口，则应通过调用 [AtlAdvise](reference/connection-point-global-functions.md#atladvise) 或 [CComPtrBase：： advise](../atl/reference/ccomptrbase-class.md#advise)来建议事件源。 你将需要自行跟踪由调用返回的 cookie。 调用 [AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise) 断开连接。

如果使用或来实现调度接口 `IDispEventImpl` `IDispEventSimpleImpl` ，则应通过调用 IDispEventSimpleImpl 来建议事件源 [：:D ispeventadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)。 调用 [IDispEventSimpleImpl：:D ispeventunadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise) 断开连接。

如果使用 `IDispEventImpl` 作为复合控件的基类，则会建议使用 [CComCompositeControl：： AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)自动通知和 unadvised 接收器映射中列出的事件源。

`IDispEventImpl`和 `IDispEventSimpleImpl` 类管理 cookie。

## <a name="see-also"></a>请参阅

[事件处理](../atl/event-handling-and-atl.md)
