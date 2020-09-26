---
title: ATL 控件包含常见问题
ms.date: 11/04/2016
helpviewer_keywords:
- hosting controls using ATL
- ActiveX control containers [C++], ATL control hosting
- ATL, hosting ActiveX controls
- ActiveX controls [C++], hosting
- controls [ATL]
ms.assetid: d4bdfbe0-82ca-4f2f-bb95-cb89bdcc9b53
ms.openlocfilehash: 693617589f157d352972485396777cec587a5b8f
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "91352694"
---
# <a name="atl-control-containment-faq"></a>ATL 控件包含常见问题

## <a name="which-atl-classes-facilitate-activex-control-containment"></a>哪些 ATL 类促进 ActiveX 控件包含？

ATL 的控件托管代码不要求使用任何 ATL 类;只需创建一个 **"AtlAxWin80"** 窗口，并根据需要使用控制宿主 API (有关详细信息，请参阅 **什么是 ATL 控件托管 api**。 但是，以下类使包含功能更易于使用。

|类|说明|
|-----------|-----------------|
|[CAxWindow](../atl/reference/caxwindow-class.md)|包装 **"AtlAxWin80"** 窗口，提供用于创建窗口、创建控件和/或将控件附加到窗口的方法，以及检索主机对象上的接口指针。|
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|包装 **"AtlAxWinLic80"** 窗口，提供创建窗口、创建控件和/或将授权控件附加到窗口的方法，以及检索主机对象上的接口指针的方法。|
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|作为基于对话框资源的 ActiveX 控件类的基类。 此类控件可以包含其他 ActiveX 控件。|
|[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)|作为基于对话框资源的对话框类的基类。 此类对话框可以包含 ActiveX 控件。|
|[CWindow](../atl/reference/cwindow-class.md)|提供一个方法 [GetDlgControl](../atl/reference/cwindow-class.md#getdlgcontrol)，该方法在给定其主机窗口的 ID 的情况下，将返回控件上的接口指针。 此外，公开的 Windows API 包装器 `CWindow` 通常使窗口管理更容易。|

## <a name="what-is-the-atl-control-hosting-api"></a>什么是 ATL 控件承载 API？

ATL 的控制宿主 API 是一组允许任何窗口充当 ActiveX 控件容器的函数。 这些函数可以静态或动态链接到您的项目中，因为它们可用作源代码并由 ATL90.dll 公开。 下表列出了控件宿主函数。

|函数|说明|
|--------------|-----------------|
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|创建一个宿主对象，将它连接到提供的窗口，然后附加现有的控件。|
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|创建一个宿主对象，将它连接到提供的窗口，然后加载一个控件。|
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|创建许可的 ActiveX 控件，对其进行初始化，并将其托管在指定窗口中，类似于 [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)。|
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|创建一个宿主对象，将它连接到提供的窗口，然后加载一个控件 (还允许) 设置事件接收器。|
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|创建许可的 ActiveX 控件，对其进行初始化，并将其托管在指定窗口中，类似于 [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)。|
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|从对话框资源创建无模式对话框并返回窗口句柄。|
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|从对话框资源创建模式对话框。|
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|返回窗口中承载的控件的 **IUnknown** 接口指针。|
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|返回连接到窗口的主机对象的 **IUnknown** 接口指针。|
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|初始化控件承载代码。|
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|取消控件托管代码。|

`HWND`前三个函数中的参数必须是 (几乎) 任何类型的现有窗口。 如果这三个函数中的任何一种显式调用 (通常情况下，您不必) ，不会将句柄传递给已作为主机 (的窗口，如果您这样做，则不会将现有宿主对象释放) 。

前七个函数隐式调用 [AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) 。

> [!NOTE]
> 控件托管 API 构成了 ATL 对 ActiveX 控件包含的支持的基础。 但是，如果你充分利用或充分利用 ATL 的包装器类，则通常不需要直接调用这些函数。 有关详细信息，请参阅 [哪些 ATL 类有助于 ActiveX 控件包含](#which-atl-classes-facilitate-activex-control-containment)。

## <a name="what-is-atlaxwin100"></a>什么是 AtlAxWin100？

`AtlAxWin100` 是帮助提供 ATL 的控件承载功能的窗口类的名称。 当你创建此类的实例时，窗口过程将自动使用控件承载 API 来创建与窗口关联的宿主对象，并使用指定为窗口标题的控件加载该对象。

## <a name="when-do-i-need-to-call-atlaxwininit"></a>何时需要调用 AtlAxWinInit？

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) 注册 **"AtlAxWin80"** 窗口类 (加上几个自定义窗口消息) 因此，在尝试创建宿主窗口之前必须调用此函数。 但是，不一定要显式调用此函数，因为宿主 Api (和使用它们的类) 常常为你调用此函数。 多次调用此函数不会有任何损害。

## <a name="what-is-a-host-object"></a>什么是宿主对象？

宿主对象是一个 COM 对象，表示 ATL 针对特定窗口提供的 ActiveX 控件容器。 宿主对象为容器窗口提供子类，使其能够反映控件的消息，并提供控件所需的必要容器接口，并公开 [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) 和 [IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) 接口，以便可以配置控件的环境。

您可以使用宿主对象来设置容器的环境属性。

## <a name="can-i-host-more-than-one-control-in-a-single-window"></a>是否可在单个窗口中承载多个控件？

不能在一个 ATL 宿主窗口中承载多个控件。 每个主机窗口一次只包含一个控件 (这允许使用一种简单的机制来处理消息反射和) 的按控件环境属性。 但是，如果你需要用户在单个窗口中查看多个控件，则将多个主机窗口创建为该窗口的子级是一个简单的事。

## <a name="can-i-reuse-a-host-window"></a>是否可重复使用宿主窗口？

不建议重复使用主机窗口。 若要确保代码的可靠性，应将宿主窗口的生存期与单个控件的生存期关联。

## <a name="when-do-i-need-to-call-atlaxwinterm"></a>何时需要调用 AtlAxWinTerm？

[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm) 注销 **"AtlAxWin80"** 窗口类。 如果不再需要在所有现有的主机窗口被销毁后创建宿主 windows) ，则应 (调用此函数。 如果不调用此函数，则在进程终止时将自动注销窗口类。

## <a name="hosting-activex-controls-using-atl-axhost"></a>使用 ATL AXHost 承载 ActiveX 控件

本节中的示例演示如何创建 AXHost，以及如何使用各种 ATL 函数托管 ActiveX 控件。 它还演示了如何使用 [IDispEventImpl](../atl/reference/idispeventimpl-class.md)) 从承载的控件访问控件和接收器 (事件。 该示例在主窗口或子窗口中承载 Calendar 控件。

请注意符号的定义 `USE_METHOD` 。 您可以更改此符号的值，使其在1和8之间有所不同。 符号的值决定了将如何创建控件：

- 对于的偶数值 `USE_METHOD` ，创建宿主的调用将向窗口提供子类，并将其转换为控制宿主。 对于奇数值，代码会创建一个充当宿主的子窗口。

- 对于 `USE_METHOD` 介于1和4之间的值，访问控件和事件接收将在创建主机的调用中完成。 介于5和8之间的值在主机上查询接口并挂钩接收器。

摘要如下：

|USE_METHOD|主机|控制访问和事件接收|已演示函数|
|-----------------|----------|--------------------------------------|---------------------------|
|1|子窗口|一个步骤|CreateControlLicEx|
|2|主窗口|一个步骤|AtlAxCreateControlLicEx|
|3|子窗口|一个步骤|CreateControlEx|
|4|主窗口|一个步骤|AtlAxCreateControlEx|
|5|子窗口|多个步骤|CreateControlLic|
|6|主窗口|多个步骤|AtlAxCreateControlLic|
|7|子窗口|多个步骤|CreateControl|
|8|主窗口|多个步骤|AtlAxCreateControl|

[!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]

## <a name="see-also"></a>另请参阅

[控件包含常见问题](../atl/atl-control-containment-faq.md)<br/>
[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)<br/>
[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)<br/>
[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[CAxWindow2T 类](../atl/reference/caxwindow2t-class.md)<br/>
[IAxWinHostWindowLic 接口](../atl/reference/iaxwinhostwindowlic-interface.md)
