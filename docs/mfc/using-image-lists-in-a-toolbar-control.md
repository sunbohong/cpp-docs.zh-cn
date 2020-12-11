---
description: 了解详细信息：在工具栏控件中使用图像列表
title: 在工具栏控件中使用图像列表
ms.date: 11/04/2016
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
ms.openlocfilehash: dbdac26f1d17997e14ed4ba16875ef3794e46a71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154430"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>在工具栏控件中使用图像列表

默认情况下，工具栏控件中的按钮所使用的图像存储为单个位图。 但是，还可以将按钮图像存储在一组图像列表中。 Toolbar 控件对象最多可以使用三个单独的图像列表：

- 启用的图像列表包含当前启用的工具栏按钮的图像。

- 禁用的图像列表包含当前已禁用的工具栏按钮图像。

- 突出显示的图像列表包含当前突出显示的工具栏按钮图像。 此图像列表仅在工具栏使用 TBSTYLE_FLAT 样式时使用。

将这些图像列表与对象相关联时，它们将由 toolbar 控件使用 `CToolBarCtrl` 。 此关联是通过调用 [CToolBarCtrl：： SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist)、 [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist)和 [SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist)来实现的。

默认情况下，MFC 使用 `CToolBar` 类实现 MFC 应用程序工具栏。 但是， `GetToolBarCtrl` 可以使用成员函数检索嵌入的 `CToolBarCtrl` 对象。 然后，可以 `CToolBarCtrl` 使用返回的对象对成员函数进行调用。

下面的示例通过将已启用的 (`m_ToolBarImages`) 和禁用 (`m_ToolBarDisabledImages`) 图像列表分配到 `CToolBarCtrl` 对象 () 来演示此方法 `m_ToolBarCtrl` 。

[!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]

> [!NOTE]
> 工具栏对象使用的图像列表必须是永久对象。 出于此原因，它们通常是 MFC 类的数据成员;在此示例中，为主框架窗口类。

图像列表与对象关联后 `CToolBarCtrl` ，框架会自动显示适当的按钮图像。

## <a name="see-also"></a>请参阅

[使用 CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[控件](../mfc/controls-mfc.md)
