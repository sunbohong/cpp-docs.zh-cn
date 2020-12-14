---
description: 了解详细信息：工具栏基础知识
title: 工具栏基础知识
ms.date: 11/04/2016
f1_keywords:
- RT_TOOLBAR
helpviewer_keywords:
- embedding toolbar in frame window class [MFC]
- application wizards [MFC], installing default application toolbars
- toolbars [MFC], creating
- resources [MFC], toolbar
- toolbar controls [MFC], toolbars created using Application Wizard
- toolbar controls [MFC], command ID
- RT_TOOLBAR resource [MFC]
- toolbars [MFC], adding default using Application Wizard
- LoadBitmap method [MFC], toolbars
- Toolbar editor [MFC], Application Wizard
- command IDs [MFC], toolbar buttons
- SetButtons method [MFC]
- CToolBar class [MFC], default toolbars in Application Wizard
- frame window classes [MFC], toolbar embedded in
- LoadToolBar method [MFC]
ms.assetid: cc00aaff-8a56-433b-b0c0-b857d76b4ffd
ms.openlocfilehash: ed52c5878482f2ff0fa1c31a133fd2948d21a76e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264383"
---
# <a name="toolbar-fundamentals"></a>工具栏基础知识

本文介绍了基本 MFC 实现，通过在应用程序向导中选择一个选项，可以将默认工具栏添加到应用程序。 涵盖的主题包括：

- [应用程序向导工具栏选项](#_core_the_appwizard_toolbar_option)

- [代码中的工具栏](#_core_the_toolbar_in_code)

- [编辑工具栏资源](#_core_editing_the_toolbar_resource)

- [多个工具栏](#_core_multiple_toolbars)

## <a name="the-application-wizard-toolbar-option"></a><a name="_core_the_appwizard_toolbar_option"></a> 应用程序向导工具栏选项

若要获取具有默认按钮的单个工具栏，请在标记为 "用户界面功能" 的页面上选择 "标准停靠工具栏" 选项。 这会将代码添加到你的应用程序中：

- 创建工具栏对象。

- 管理工具栏，包括其停靠或浮动的能力。

## <a name="the-toolbar-in-code"></a><a name="_core_the_toolbar_in_code"></a> 代码中的工具栏

工具栏是声明为应用程序类的数据成员的 [CToolBar](../mfc/reference/ctoolbar-class.md) 对象 `CMainFrame` 。 换句话说，toolbar 对象嵌入在主框架窗口对象中。 这意味着 MFC 会在创建框架窗口时创建工具栏，并在销毁框架窗口时销毁工具栏。 下面的分部类声明对于多文档界面 (MDI) 应用程序，显示嵌入工具栏和嵌入式状态栏的数据成员。 它还显示成员函数的重写 `OnCreate` 。

[!code-cpp[NVC_MFCListView#6](../atl/reference/codesnippet/cpp/toolbar-fundamentals_1.h)]

工具栏创建发生在中 `CMainFrame::OnCreate` 。 MFC 在为框架创建窗口之后但在它变得可见之前，将调用 [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 。 `OnCreate`应用程序向导生成的默认值为以下工具栏任务：

1. 调用 `CToolBar` 对象的 [create](../mfc/reference/ctoolbar-class.md#create) 成员函数以创建基础 [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) 对象。

1. 调用 [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) 以加载工具栏资源信息。

1. 调用函数以启用停靠、浮动和工具提示。 有关这些调用的详细信息，请参阅文章 [停靠和浮动工具栏](../mfc/docking-and-floating-toolbars.md)。

> [!NOTE]
> MFC 常规示例 [DOCKTOOL](../overview/visual-cpp-samples.md) 包括新的和新的 mfc 工具栏的插图。 使用的工具栏 `COldToolbar` 要求步骤2中的调用 `LoadBitmap` (，而不是 `LoadToolBar`) 和到 `SetButtons` 。 新工具栏需要对的调用 `LoadToolBar` 。

停靠、浮动和工具提示调用是可选的。 如果愿意，可以从中删除这些行 `OnCreate` 。 结果是保持固定的工具栏，不能浮动或 redock 并且无法显示工具提示。

## <a name="editing-the-toolbar-resource"></a><a name="_core_editing_the_toolbar_resource"></a> 编辑工具栏资源

使用应用程序向导获得的默认工具栏基于 MFC 版本4.0 中引入的 **RT_TOOLBAR** 自定义资源。 可以用 [工具栏编辑器](../windows/toolbar-editor.md)来编辑此资源。 利用编辑器，您可以轻松地添加、删除和重排按钮。 它包含与 Visual C++ 中的常规图形编辑器非常相似的按钮的图形编辑器。 如果在早期版本的 Visual C++ 中编辑了工具栏，则现在可以更轻松地找到该任务。

若要将工具栏按钮连接到命令，请为按钮指定命令 ID，如 `ID_MYCOMMAND` 。 在工具栏编辑器的按钮的属性页中指定命令 ID。 然后为命令创建处理程序函数 (参阅 [将消息映射到函数](../mfc/reference/mapping-messages-to-functions.md) 以了解详细信息) 。

New [CToolBar](../mfc/reference/ctoolbar-class.md) 成员函数与 **RT_TOOLBAR** 资源一起使用。 [LoadToolBar](../mfc/reference/ctoolbar-class.md#loadtoolbar) 现在使用 [LoadBitmap](../mfc/reference/ctoolbar-class.md#loadbitmap) 来加载工具栏按钮图像的位图，使用 [SetButtons](../mfc/reference/ctoolbar-class.md#setbuttons) 设置按钮样式，并使用位图图像连接按钮。

有关使用工具栏编辑器的详细信息，请参阅 [工具栏编辑器](../windows/toolbar-editor.md)。

## <a name="multiple-toolbars"></a><a name="_core_multiple_toolbars"></a> 多个工具栏

应用程序向导为您提供了一个默认工具栏。 如果在应用程序中需要多个工具栏，可以根据默认工具栏的向导生成的代码，为其他工具栏编写代码模型。

如果希望将工具栏显示为命令的结果，则需要：

- 使用工具栏编辑器创建新的工具栏资源，并将其加载到 `OnCreate` [LoadToolbar](../mfc/reference/ctoolbar-class.md#loadtoolbar) 成员函数中。

- 在主框架窗口类中嵌入一个新的 [CToolBar](../mfc/reference/ctoolbar-class.md) 对象。

- 使适当的函数在中调用 `OnCreate` 以停靠或浮动工具栏，设置其样式，等等。

### <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [MFC 工具栏实现 (工具栏上的概述信息) ](../mfc/mfc-toolbar-implementation.md)

- [停靠和浮动工具栏](../mfc/docking-and-floating-toolbars.md)

- [工具栏工具提示](../mfc/toolbar-tool-tips.md)

- [CToolBar](../mfc/reference/ctoolbar-class.md)和[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)类

- [使用工具栏控件](../mfc/working-with-the-toolbar-control.md)

- [使用旧工具栏](../mfc/using-your-old-toolbars.md)

## <a name="see-also"></a>请参阅

[MFC 工具栏实现](../mfc/mfc-toolbar-implementation.md)
