---
description: 了解更多相关信息：滚动和缩放视图
title: 滚动和缩放视图
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [MFC]
- scaling views [MFC]
- message handling [MFC], scroll bars in view class [MFC]
- scroll bars [MFC], messages
- scrolling views [MFC]
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
ms.openlocfilehash: f18b774eadf875f61fcb1f3f3a8dc9e0e370f9a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217804"
---
# <a name="scrolling-and-scaling-views"></a>滚动和缩放视图

MFC 支持滚动和视图的视图，这些视图自动缩放到显示这些视图的框架窗口的大小。 类 `CScrollView` 支持这两种视图。

有关滚动和缩放的详细信息，请参阅 *MFC 参考* 中的 [CScrollView](../mfc/reference/cscrollview-class.md)类。 对于滚动示例，请参阅 [自由绘制的示例](../overview/visual-cpp-samples.md)。

## <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- 滚动视图

- 缩放视图

- [查看坐标](/windows/win32/gdi/window-coordinate-system)

## <a name="scrolling-a-view"></a><a name="_core_scrolling_a_view"></a> 滚动视图

文档的大小通常大于其视图可以显示的大小。 出现这种情况的原因可能是文档的数据增加或用户缩小了显示视图的窗口。 在这种情况下，视图必须支持滚动。

任何视图都可以处理其 `OnHScroll` 和成员函数中的滚动条消息 `OnVScroll` 。 您可以在这些函数中实现滚动条消息处理、自行执行所有工作，或者可以使用 `CScrollView` 类来处理滚动。

`CScrollView` 执行下列操作：

- 管理窗口和视区大小和映射模式

- 自动滚动以响应滚动条消息

当用户在滚动条) 轴上单击时，可以指定滚动的 "页面" (量，当用户单击滚动箭头) 时，可以指定 "直线" (。 规划这些值，以适合您的视图的性质。 例如，您可能希望以1像素为增量为图形视图滚动，但以文本文档中的行高为增量。

## <a name="scaling-a-view"></a><a name="_core_scaling_a_view"></a> 缩放视图

如果希望视图自动适应框架窗口的大小，则可以使用 `CScrollView` 进行缩放而不是滚动。 将对逻辑视图进行拉伸或收缩，以精确地适应窗口的工作区。 缩放视图没有滚动条。

## <a name="see-also"></a>请参阅

[使用视图](../mfc/using-views.md)
