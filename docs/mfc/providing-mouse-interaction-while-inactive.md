---
description: 了解详细信息：在不活动时提供鼠标交互
title: 不活动时提供鼠标交互
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], mouse interaction
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
ms.openlocfilehash: bd3c069b052b58059de5f311e4ead795400d32fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248731"
---
# <a name="providing-mouse-interaction-while-inactive"></a>不活动时提供鼠标交互

如果控件不是立即激活的，则您可能仍希望它处理 WM_SETCURSOR 和 WM_MOUSEMOVE 消息，即使控件没有自己的窗口也是如此。 这可以通过 `COleControl` 实现接口的实现来实现 `IPointerInactive` ，默认情况下已禁用。 有关此接口的说明，请参阅 *ACTIVEX SDK* (。 ) 若要启用它，请在 [COleControl：： GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags)返回的一组标志中包含 pointerInactive 标志：

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#10](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_3.cpp)]

如果在通过 **MFC ActiveX 控件向导** 创建控件时在 "[控件设置](../mfc/reference/control-settings-mfc-activex-control-wizard.md)" 页上选择 "不 **活动时鼠标指针通知**" 选项，则会自动生成包含此标志的代码。

`IPointerInactive`启用接口后，容器委托 WM_SETCURSOR 并向其 WM_MOUSEMOVE 消息。 `COleControl`的实现在 `IPointerInactive` 相应地调整鼠标坐标后，通过控件的消息映射调度消息。 您可以通过将相应的条目添加到消息映射来处理消息，就像普通的窗口消息。 在这些消息的处理程序中，避免使用 *m_hWnd* 成员变量 (或使用该变量的任何成员函数) ，而不首先检查其值是否不为 **NULL**。

您还可能希望将非活动控件作为 OLE 拖放操作的目标。 这需要在用户将对象拖到控件上时激活控件，使控件的窗口可以注册为拖放目标。 若要导致在拖动过程中发生激活，请重写 [COleControl：： GetActivationPolicy](../mfc/reference/colecontrol-class.md#getactivationpolicy)，并返回 POINTERINACTIVE_ACTIVATEONDRAG 标志：

[!code-cpp[NVC_MFC_AxOpt#11](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_4.cpp)]

启用 `IPointerInactive` 接口通常意味着您希望控件始终能够处理鼠标消息。 若要在不支持接口的容器中获取此行为 `IPointerInactive` ，需要在可见时始终激活控件，这意味着控件应在其杂项标志中包含 OLEMISC_ACTIVATEWHENVISIBLE 标志。 但是，若要防止此标志在支持的容器中生效 `IPointerInactive` ，还可以指定 OLEMISC_IGNOREACTIVATEWHENVISIBLE 标志：

[!code-cpp[NVC_MFC_AxOpt#12](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_5.cpp)]

## <a name="see-also"></a>请参阅

[MFC ActiveX 控件：优化](../mfc/mfc-activex-controls-optimization.md)
