---
description: 了解有关以下内容的详细信息：树控件拖放操作
title: 树控件拖放操作
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], drag and drop operations
- drag and drop [MFC], CTreeCtrl
- tree controls [MFC], drag and drop operations
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
ms.openlocfilehash: 000255ad4aa6801cbe27676603a3f42d0abbef30
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264175"
---
# <a name="tree-control-drag-and-drop-operations"></a>树控件拖放操作

在用户开始拖动项时， ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 的树控件将发送通知。 当用户使用鼠标左键开始拖动项时，控件将发送 [TVN_BEGINDRAG](/windows/win32/Controls/tvn-begindrag) 通知消息，当用户使用右按钮开始拖动时，控件将发送 [TVN_BEGINRDRAG](/windows/win32/Controls/tvn-beginrdrag) 通知消息。 通过为树控件提供 TVS_DISABLEDRAGDROP 样式，可以防止树控件发送这些通知。

在拖动操作过程中，通过调用 [CreateDragImage](../mfc/reference/ctreectrl-class.md#createdragimage) 成员函数来获取要显示的图像。 树控件将基于所拖动的项标签创建一个拖动位图。 然后，树形控件创建一个图像列表，向其中添加位图，并返回指向 [CImageList](../mfc/reference/cimagelist-class.md) 对象的指针。

必须提供实际拖动项的代码。 这通常涉及使用图像列表函数的拖动功能并处理 [WM_MOUSEMOVE](/windows/win32/inputdev/wm-mousemove) ，并 [WM_LBUTTONUP](/windows/win32/inputdev/wm-lbuttonup) (或) [WM_RBUTTONUP](/windows/win32/inputdev/wm-rbuttonup) 在拖动操作开始后发送的消息。 有关图像列表函数的详细信息，请参阅 Windows SDK 中 " *MFC 参考*" 和 "[图像" 列表](/windows/win32/controls/image-lists)中的 [CImageList](../mfc/reference/cimagelist-class.md) 。 有关拖动树控件项的详细信息，请参阅 "Windows SDK 中的 [拖动树视图项](/windows/win32/Controls/tree-view-controls)。

如果树控件中的项是拖放操作的目标，则需要了解鼠标光标何时指向了目标项。 可以通过调用 [system.windows.media.visualtreehelper.hittest](../mfc/reference/ctreectrl-class.md#hittest) 成员函数来了解。 指定点和整数，或指定包含鼠标光标当前坐标的 [TVHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-tvhittestinfo) 结构的地址。 当函数返回时，该整数或结构包含一个指示与树控件相关的鼠标光标的位置的标志。 如果光标在树控件中的某个项的上方，则该结构还包含该项的句柄。

可以通过调用 [SetItem](../mfc/reference/ctreectrl-class.md#setitem) 成员函数将状态设置为值，指示项是拖放操作的目标 `TVIS_DROPHILITED` 。 使用用于指示拖放目标的样式绘制具有此状态的项。

## <a name="see-also"></a>请参阅

[使用 CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[控件](../mfc/controls-mfc.md)
