---
description: 了解详细信息：滑块通知消息
title: 滑块通知消息
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], notifications
- slider controls [MFC], notification messages
- messages, notification
- notifications [MFC], CSliderCtrl
ms.assetid: b9121104-3889-4a10-92bf-f3723f1af9d0
ms.openlocfilehash: fab8d515e71fd2ca8fd390a41b6d1bf68442c24c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216881"
---
# <a name="slider-notification-messages"></a>滑块通知消息

滑块控件根据滑块控件的方向发送父级 WM_HSCROLL 或 WM_VSCROLL 消息，通知其父窗口的用户操作。 若要处理这些消息，请向父窗口添加 WM_HSCROLL 和 WM_VSCROLL 消息的处理程序。 将向 [OnHScroll](../mfc/reference/cwnd-class.md#onhscroll) 和 [OnVScroll](../mfc/reference/cwnd-class.md#onvscroll) 成员函数传递通知代码、滑块的位置以及指向 [CSliderCtrl](../mfc/reference/csliderctrl-class.md) 对象的指针。 请注意，指针的类型为， `CScrollBar *` 即使它指向对象也是如此 `CSliderCtrl` 。 如果需要操作滑块控件，则可能需要转换此指针。

滑块控件不使用滚动条通知代码，而是发送一组不同的通知代码。 仅当用户使用键盘与滑块控件交互时，滑块控件才能发送 TB_BOTTOM、TB_LINEDOWN、TB_LINEUP 和 TB_TOP 通知代码。 仅当用户使用鼠标时才发送 TB_THUMBPOSITION 和 TB_THUMBTRACK 通知消息。 在这两种情况下都将发送 TB_ENDTRACK、TB_PAGEDOWN 和 TB_PAGEUP 通知代码。

下表列出了滑块控件通知消息和事件 (虚拟键代码或鼠标事件，这些事件) 导致发送通知。 （有关标准虚拟键代码的列表，请参见 Winuser.h。）

|通知消息|导致发送通知的事件|
|--------------------------|-------------------------------------------|
|TB_BOTTOM|VK_END|
|TB_ENDTRACK|WM_KEYUP (用户释放了发送相关虚拟密钥代码的密钥) |
|TB_LINEDOWN|VK_RIGHT 或 VK_DOWN|
|TB_LINEUP|VK_LEFT 或 VK_UP|
|TB_PAGEDOWN|VK_NEXT (用户单击此滑块下方或右侧的通道) |
|TB_PAGEUP|VK_PRIOR 用户 (单击滑块上方或左侧的通道) |
|TB_THUMBPOSITION|WM_LBUTTONUP 以下 TB_THUMBTRACK 通知消息|
|TB_THUMBTRACK| (用户将滑块拖动) |
|TB_TOP|VK_HOME|

## <a name="see-also"></a>请参阅

[使用 CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[控件](../mfc/controls-mfc.md)
