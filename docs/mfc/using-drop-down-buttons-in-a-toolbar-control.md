---
description: 了解详细信息：使用工具栏控件中的 Drop-Down 按钮
title: 使用工具栏控件中的下拉按钮
ms.date: 11/04/2016
f1_keywords:
- TBN_DROPDOWN
- TBSTYLE_EX_DRAWDDARROWS
helpviewer_keywords:
- CToolBarCtrl class [MFC], drop-down buttons
- toolbars [MFC], drop-down buttons
- drop-down buttons in toolbars
- TBSTYLE_EX_DRAWDDARROWS
- TBN_DROPDOWN notification [MFC]
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
ms.openlocfilehash: a37f39397f6b6f66bed1ad1d2fbd9530b55f3d7b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154456"
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>使用工具栏控件中的下拉按钮

除了标准推送按钮外，工具栏还可以具有下拉按钮。 下拉按钮通常由附加向下箭头指示。

> [!NOTE]
> 仅当设置了 TBSTYLE_EX_DRAWDDARROWS 扩展样式后，才会显示附加的向下箭头。

当用户单击此箭头 (或按钮本身时，如果) 没有箭头，TBN_DROPDOWN 通知消息将发送到 toolbar 控件的父级。 然后，你可以处理此通知并显示一个弹出菜单;与 Internet Explorer 的行为类似。

下面的过程演示如何使用弹出菜单实现下拉工具栏按钮：

### <a name="to-implement-a-drop-down-button"></a>实现下拉按钮

1. `CToolBarCtrl`创建对象后，请使用以下代码设置 TBSTYLE_EX_DRAWDDARROWS 样式：

   [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]

1. 为任何新的 ([InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) 或 [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)) 或现有 ([SetButtonInfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) 按钮设置 TBSTYLE_DROPDOWN 样式，这些按钮将成为下拉按钮。 下面的示例演示如何修改对象中的现有按钮 `CToolBarCtrl` ：

   [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]

1. 将 TBN_DROPDOWN 处理程序添加到 toolbar 对象的父类。

   [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]

1. 在新处理程序中，显示相应的弹出菜单。 下面的代码演示了一种方法：

   [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]

## <a name="see-also"></a>请参阅

[使用 CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[控件](../mfc/controls-mfc.md)
