---
description: 了解更多相关信息：工具栏工具提示
title: 工具栏工具提示
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], activating
- CBRS_TOOLTIPS constant [MFC]
- tool tips [MFC], adding text
- updates [MFC]
- CBRS_FLYBY constant [MFC]
- tool tips [MFC]
- updating status bar messages
- updates, status bar messages
- status bars [MFC], tool tips
- flyby status bar updates
ms.assetid: d1696305-b604-4fad-9f09-638878371412
ms.openlocfilehash: bbf60246e778b60c2a6eacbcb55441806c00fad2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264279"
---
# <a name="toolbar-tool-tips"></a>工具栏工具提示

工具提示是在将鼠标悬停在某个时间段的按钮上时，显示工具栏按钮用途简短说明的小弹出窗口。 使用带有工具栏的应用程序向导创建应用程序时，将为你提供工具提示支持。 本文介绍应用程序向导创建的工具提示支持以及如何向应用程序添加工具提示支持。

本文介绍：

- [激活工具提示](#_core_activating_tool_tips)

- [越过状态栏更新](#_core_fly_by_status_bar_updates)

## <a name="activating-tool-tips"></a><a name="_core_activating_tool_tips"></a> 激活工具提示

若要在应用程序中激活工具提示，必须执行以下两项操作：

- 将 CBRS_TOOLTIPS 样式添加到其他样式中 (例如 WS_CHILD、WS_VISIBLE 和其他 **CBRS_** 样式，) 将作为 *dwStyle* 参数传递到 [CToolBar：： Create](../mfc/reference/ctoolbar-class.md#create) 函数或 [SetBarStyle](../mfc/reference/ccontrolbar-class.md#setbarstyle)中。

- 如下面的过程所述，将工具栏提示文本追加 ( "\n" ) 中，并将其附加到包含工具栏命令的命令行提示的字符串资源。 字符串资源共享工具栏按钮的 ID。

#### <a name="to-add-the-tool-tip-text"></a>添加工具提示文本

1. 在工具栏编辑器中编辑工具栏时，打开给定按钮的 **工具栏按钮 "属性** " 窗口。

1. 在 " **提示** " 框中，指定要在该按钮的工具提示中显示的文本。

> [!NOTE]
> 在工具栏编辑器中将文本设置为 button 属性将替换前面的过程，在此过程中，您必须打开和编辑字符串资源。

如果启用了工具提示的控件条上有子控件，则只要控件栏满足以下条件，控件条就会在控件条上显示每个子控件的工具提示：

- 控件的 ID 不为-1。

- 与资源文件中的子控件具有相同 ID 的字符串表项具有工具提示字符串。

## <a name="flyby-status-bar-updates"></a><a name="_core_fly_by_status_bar_updates"></a> 越过状态栏更新

与工具提示相关的一项功能是 "越过" 状态栏更新。 默认情况下，当按钮被激活时，状态栏上的消息仅描述特定的工具栏按钮。 通过将 CBRS_FLYBY 包含在传递到的样式列表中 `CToolBar::Create` ，可以在鼠标光标移到工具栏而不实际激活按钮时更新这些消息。

### <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [MFC 工具栏实现 (工具栏上的概述信息) ](../mfc/mfc-toolbar-implementation.md)

- [停靠和浮动工具栏](../mfc/docking-and-floating-toolbars.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md)和[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)类

- [使用工具栏控件](../mfc/working-with-the-toolbar-control.md)

- [使用旧工具栏](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>请参阅

[MFC 工具栏实现](../mfc/mfc-toolbar-implementation.md)
