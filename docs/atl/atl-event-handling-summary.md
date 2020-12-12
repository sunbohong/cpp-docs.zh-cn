---
description: 了解详细信息： ATL 事件处理摘要
title: ATL 事件处理摘要
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
ms.openlocfilehash: c041de6cbd0e0852d5ce0e51d892c21c7d9a23d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148650"
---
# <a name="atl-event-handling-summary"></a>ATL 事件处理摘要

通常，处理 COM 事件是一个相对简单的过程。 有三个主要步骤：

- 在对象上实现事件接口。

- 建议你的对象要接收事件的事件源。

- 当对象不再需要接收事件时，Unadvise 事件源。

## <a name="implementing-the-interface"></a>实现接口

使用 ATL 实现接口有四种主要方法。

|派生自 |适用于接口类型|要求您实现所有方法 *|在运行时需要一个类型库|
|-----------------|---------------------------------|---------------------------------------------|-----------------------------------------|
|接口|Vtable|是|否|
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|双|是|是|
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|调度接口|否|是|
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|调度接口|否|否|

\* 使用 ATL 支持类时，永远不需要 `IUnknown` 手动实现或 `IDispatch` 方法。

## <a name="advising-and-unadvising-the-event-source"></a>通知和 Unadvising 事件源

有三种主要方法可使用 ATL 通知和 unadvising 事件源。

|Advise 函数|Unadvise 函数|最适合用于|需要跟踪 cookie|注释|
|---------------------|-----------------------|--------------------------------|---------------------------------------------|--------------|
|[AtlAdvise](reference/connection-point-global-functions.md#atladvise)， [CComPtrBase：： Advise](../atl/reference/ccomptrbase-class.md#advise)|[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)|Vtable 或双重接口|是|`AtlAdvise` 是全局 ATL 函数。 `CComPtrBase::Advise` 由 [CComPtr](../atl/reference/ccomptr-class.md) 和 [CComQIPtr](../atl/reference/ccomqiptr-class.md)使用。|
|[IDispEventSimpleImpl：:D ispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)|[IDispEventSimpleImpl：:D ispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) 或 [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|否|参数少于 `AtlAdvise` ，因为基类执行更多操作。|
|[CComCompositeControl：： AdviseSinkMap (TRUE) ](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|[CComCompositeControl：： AdviseSinkMap (FALSE) ](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|复合控件中的 ActiveX 控件|否|`CComCompositeControl::AdviseSinkMap` 建议事件接收器映射中的所有条目。 同一函数 unadvises 条目。 此方法由类自动调用 `CComCompositeControl` 。|
|[CAxDialogImpl：： AdviseSinkMap (TRUE) ](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|[CAxDialogImpl：： AdviseSinkMap (FALSE) ](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|对话框中的 ActiveX 控件|否|`CAxDialogImpl::AdviseSinkMap` 在对话框资源中建议和 unadvises 所有 ActiveX 控件。 这是自动完成的。|

## <a name="see-also"></a>请参阅

[事件处理](../atl/event-handling-and-atl.md)<br/>
[支持 IDispEventImpl](../atl/supporting-idispeventimpl.md)
