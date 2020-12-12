---
description: 了解详细信息：使用带有 Rebar 控件的对话栏
title: 对 Rebar 控件使用对话栏
ms.date: 11/04/2016
helpviewer_keywords:
- WS_EX_TRANSPARENT style
- rebar controls [MFC], dialog bars
- dialog bars [MFC], using with rebar bands
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
ms.openlocfilehash: 97fb8ca5c356d91fa4b4ba44753fbdc9bf298435
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263525"
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>对 Rebar 控件使用对话栏

如 [Rebar 控件和带区](../mfc/rebar-controls-and-bands.md)中所述，每个带区只能包含一个子窗口 (或控制) 。 如果希望每个带区包含多个子窗口，则这可能是一项限制。 一种方便的解决方法是创建具有多个控件的对话框资源，然后将包含对话栏) 的 rebar 带 (添加到 rebar 控件。

通常情况下，如果希望对话栏条带显示为透明，则可以为对话栏对象设置 WS_EX_TRANSPARENT 扩展样式。 但是，因为 WS_EX_TRANSPARENT 在正确地绘制对话栏的背景时有一些问题，您需要做一些额外的工作才能实现所需的效果。

下面的过程详细说明了在不使用 WS_EX_TRANSPARENT 扩展样式的情况下实现透明度所需的步骤。

### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>在 rebar 带区中实现透明对话栏

1. 使用 " [添加类" 对话框](../mfc/reference/adding-an-mfc-class.md)，添加一个新类 (例如， `CMyDlgBar` 实现对话栏对象的) 。

1. 为 WM_ERASEBKGND 消息添加处理程序。

1. 在新的处理程序中，修改现有代码，使其与以下示例匹配：

   [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]

1. 为 WM_MOVE 消息添加处理程序。

1. 在新的处理程序中，修改现有代码，使其与以下示例匹配：

   [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]

新的处理程序通过将 WM_ERASEBKGND 消息转发到父窗口，并在每次移动对话框对象时强制重绘来模拟对话栏的透明度。

## <a name="see-also"></a>请参阅

[使用 CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[控件](../mfc/controls-mfc.md)
