---
description: 了解更多：滑块控件成员函数
title: 滑块控件成员函数
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], methods
- slider controls [MFC], member functions
ms.assetid: dbde49ee-7306-4d14-a6ce-d09aa198178f
ms.openlocfilehash: 57108872a779bc4876be89afd5b81008f69a0837
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216894"
---
# <a name="slider-control-member-functions"></a>滑块控件成员函数

应用程序可以调用滑块控件的成员函数来检索有关滑块控件的信息 ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) 并更改其特性。

若要检索滑块的位置 (即，用户已选择) 的值，请使用 [GetPos](../mfc/reference/csliderctrl-class.md#getpos) 成员函数。 若要设置滑块的位置，请使用 [SetPos](../mfc/reference/csliderctrl-class.md#setpos) 成员函数。 随时都可以使用 `VerifyPos` 成员函数确保滑块在最小值和最大值之间。

滑块控件的范围是滑块控件可以表示的一组连续值。 大多数应用程序在第一次创建时使用 [SetRange](../mfc/reference/csliderctrl-class.md#setrange) 成员函数设置滑块控件的范围。 使用 [SetRangeMax](../mfc/reference/csliderctrl-class.md#setrangemax) 和 [SetRangeMin](../mfc/reference/csliderctrl-class.md#setrangemin) 成员函数创建滑块控件后，应用程序可以动态地更改范围。 当用户完成使用滑块控件时，允许动态更改范围的应用程序通常会检索最终范围设置。 若要检索这些设置，请使用 [GetRange](../mfc/reference/csliderctrl-class.md#getrange)、 [GetRangeMax](../mfc/reference/csliderctrl-class.md#getrangemax)和 [GetRangeMin](../mfc/reference/csliderctrl-class.md#getrangemin) 成员函数。

应用程序可以使用 TBS_AUTOTICKS 样式来自动显示滑块控件的刻度线。 不过，如果应用程序需要控制刻度线的位置或频率，则可以使用许多成员函数。

若要设置刻度线的位置，应用程序可以使用 [SetTic](../mfc/reference/csliderctrl-class.md#settic) 成员函数。 使用 [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq) 成员函数，应用程序可以设置在滑块控件范围内按固定间隔显示的刻度线。 例如，应用程序可以使用此成员函数在1到100的范围内只显示10个刻度线。

若要检索与刻度线对应的范围中的索引，请使用 [GetTic](../mfc/reference/csliderctrl-class.md#gettic) 成员函数。 [GetTicArray](../mfc/reference/csliderctrl-class.md#getticarray)成员函数检索这些索引的数组。 若要检索刻度线的位置，请使用 [GetTicPos](../mfc/reference/csliderctrl-class.md#getticpos) 成员函数。 应用程序可以使用 [GetNumTics](../mfc/reference/csliderctrl-class.md#getnumtics) 成员函数检索刻度线的数目。

[ClearTics](../mfc/reference/csliderctrl-class.md#cleartics)成员函数将移除滑块控件的所有刻度线。

滑块控件的线条大小确定在应用程序收到 TB_LINEDOWN 或 TB_LINEUP 通知消息时滑块移动的程度。 同样，页面大小决定对 TB_PAGEDOWN 和 TB_PAGEUP 通知消息的响应。 应用程序可以通过使用 [GetLineSize](../mfc/reference/csliderctrl-class.md#getlinesize)、 [SetLineSize](../mfc/reference/csliderctrl-class.md#setlinesize)、 [GetPageSize](../mfc/reference/csliderctrl-class.md#getpagesize)和 [SetPageSize](../mfc/reference/csliderctrl-class.md#setpagesize) 成员函数来检索和设置行大小和页大小值。

应用程序可以使用成员函数来检索滑块控件的尺寸。 [GetThumbRect](../mfc/reference/csliderctrl-class.md#getthumbrect)成员函数检索滑块的边框。 [GetChannelRect](../mfc/reference/csliderctrl-class.md#getchannelrect)成员函数检索滑块控件通道的边框。 通道 (是滑块在其上移动的区域，并且在选择范围时包含突出显示。 ) 

如果滑块控件具有 TBS_ENABLESELRANGE 样式，则用户可以从其选择一系列连续值。 许多成员函数允许动态调整选择范围。 [SetSelection](../mfc/reference/csliderctrl-class.md#setselection)成员函数设置所选内容的起始位置和结束位置。 当用户完成设置选择范围时，应用程序可以使用 [GetSelection](../mfc/reference/csliderctrl-class.md#getselection) 成员函数来检索设置。 若要清除用户的选择，请使用 [ClearSel](../mfc/reference/csliderctrl-class.md#clearsel) 成员函数。

## <a name="see-also"></a>请参阅

[使用 CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[控件](../mfc/controls-mfc.md)
