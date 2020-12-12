---
description: 了解详细信息：进度控件的样式
title: 进度控件的样式
ms.date: 11/19/2018
helpviewer_keywords:
- PBS_SMOOTH style
- progress controls [MFC], styles
- PBS_VERTICAL style
- CProgressCtrl class [MFC], styles
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
ms.openlocfilehash: cd6ce1093f8bd2e3271a386e894d1e8dcd1a4fd7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216491"
---
# <a name="styles-for-the-progress-control"></a>进度控件的样式

最初创建 ([CProgressCtrl：： create](../mfc/reference/cprogressctrl-class.md#create)) 的进度控件时，请使用 *dwStyle* 参数为进度控件指定所需的窗口样式。 以下列表详述了适用的窗口样式。 进度控件将忽略此处列出的窗口样式以外的所有窗口样式。 应始终将进度控件作为子窗口（通常是父对话框的子窗口）创建。

|窗口样式|效果|
|------------------|------------|
|WS_BORDER|在窗口周围创建边框。|
|WS_CHILD|创建子窗口（应始终用于 `CProgressCtrl`）。|
|WS_CLIPCHILDREN|在父窗口中绘制时，将排除子窗口占用的区域。 在创建父窗口时使用。|
|WS_CLIPSIBLINGS|相对于彼此裁剪子窗口。|
|WS_DISABLED|创建初始禁用的窗口。|
|WS_VISIBLE|创建初始可见的窗口。|
|WS_TABSTOP|指定当用户按 Tab 键来移动焦点时，进度控件可以接收焦点。|

此外，还可以指定两个仅适用于进度控件的样式，PBS_VERTICAL 和 PBS_SMOOTH。

使用 PBS_VERTICAL 垂直方向控制控件，而不是水平方向。 使用 PBS_SMOOTH 完全填充控件，而不是显示以增量方式填充控件的小型分隔的方块。

无 PBS_SMOOTH 样式：

![标准进度栏样式](../mfc/media/vc4ruw1.gif "标准进度栏样式")

具有 PBS_SMOOTH 和 PBS_VERTICAL 样式：

![进度栏样式 - 平滑和垂直](../mfc/media/vc4ruw2.gif "进度栏样式 - 平滑和垂直")

有关详细信息，请参阅 *MFC 参考* 中的 [窗口样式](../mfc/reference/styles-used-by-mfc.md#frame-window-styles-mfc)。

## <a name="see-also"></a>请参阅

[使用 CProgressCtrl](../mfc/using-cprogressctrl.md)
