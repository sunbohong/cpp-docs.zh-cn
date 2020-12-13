---
description: 了解详细信息：更改列表控件样式
title: 更改列表控件样式
ms.date: 11/04/2016
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
ms.openlocfilehash: a6712baf5ea1e161ec1fd73e25ea01fedd650670
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339730"
---
# <a name="changing-list-control-styles"></a>更改列表控件样式

您可以在创建列表控件后随时更改其窗口样式 ([CListCtrl](reference/clistctrl-class.md)) 。 通过更改窗口样式，您可以更改控件使用的视图类型。 例如，若要模拟浏览器，可以提供菜单项或工具栏按钮，用于在不同视图之间切换控件：图标视图、列表视图等。

例如，当用户选择菜单项时，可以调用 [GetWindowLong](/windows/win32/api/winuser/nf-winuser-getwindowlongw) 来检索控件的当前样式，然后调用 [SetWindowLong](/windows/win32/api/winuser/nf-winuser-setwindowlongw) 来重置样式。 有关详细信息，请参阅在 Windows SDK 中 [使用列表视图控件](/windows/win32/Controls/using-list-view-controls) 。

" [创建](reference/clistctrl-class.md#create)" 中列出了可用样式。 样式 **LVS_ICON**、 **LVS_SMALLICON**、 **LVS_LIST** 和 **LVS_REPORT** 指定四个列表控件视图。

## <a name="extended-styles"></a>扩展样式

除了列表控件的标准样式以外，还有另一组称为扩展样式。 这些样式（在 Windows SDK 中的 [扩展列表视图样式](/windows/win32/Controls/extended-list-view-styles) 中讨论）提供了各种可自定义列表控件行为的有用功能。 若要实现特定样式的行为 (例如，悬停选择) ，请调用 [CListCtrl：： SetExtendedStyle](reference/clistctrl-class.md#setextendedstyle)，并传递所需的样式。 下面的示例演示了函数调用：

[!code-cpp[NVC_MFCControlLadenDialog#22](codesnippet/cpp/changing-list-control-styles_1.cpp)]

> [!NOTE]
> 若要运行悬停选项，还必须打开 **LVS_EX_ONECLICKACTIVATE** 或 **LVS_EX_TWOCLICKACTIVATE** 。

## <a name="see-also"></a>请参阅

[使用 CListCtrl](using-clistctrl.md)<br/>
[控件](controls-mfc.md)
