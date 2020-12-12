---
description: 了解详细信息： WM_ 消息处理程序： L-M
title: WM_ 消息处理程序：L - M
ms.date: 11/04/2016
f1_keywords:
- ON_WM_MENUSELECT
- ON_WM_MBUTTONDBLCLK
- ON_WM_MOUSEACTIVATE
- ON_WM_MOUSEMOVE
- ON_WM_MOVING
- ON_WM_LBUTTONUP
- ON_WM_LBUTTONDBLCLK
- ON_WM_MEASUREITEM
- ON_WM_MDIACTIVATE
- ON_WM_MOVE
- ON_WM_LBUTTONDOWN
- ON_WM_MBUTTONDOWN
- ON_WM_MENUCHAR
- ON_WM_MBUTTONUP
helpviewer_keywords:
- ON_WM_MENUSELECT [MFC]
- ON_WM_MBUTTONDBLCLK [MFC]
- ON_WM_MOVE [MFC]
- ON_WM_MOUSEACTIVATE [MFC]
- ON_WM_MBUTTONUP [MFC]
- ON_WM_MOUSEMOVE [MFC]
- ON_WM_MENUCHAR [MFC]
- ON_WM_MBUTTONDOWN [MFC]
- ON_WM_MEASUREITEM [MFC]
- ON_WM_MOVING [MFC]
- ON_WM_LBUTTONDOWN [MFC]
- ON_WM_MDIACTIVATE [MFC]
- ON_WM_LBUTTONDBLCLK [MFC]
- ON_WM_LBUTTONUP [MFC]
- WM_ messages
ms.assetid: 96ecaaf1-6d13-4e12-a454-535635967489
ms.openlocfilehash: 2044f8eeb74c75f92f42c6e0199820528f7c10c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218324"
---
# <a name="wm_-message-handlers-l---m"></a>WM_ 消息处理程序：L - M

下面左侧的映射条目对应于右侧的函数原型：

|映射条目|函数原型|
|---------------|------------------------|
|ON_WM_LBUTTONDBLCLK ( # A1|afx_msg void [OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk) (UINT，CPoint) ;|
|ON_WM_LBUTTONDOWN ( # A1|afx_msg void [OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown) (UINT，CPoint) ;|
|ON_WM_LBUTTONUP ( # A1|afx_msg void [OnLButtonUp](../../mfc/reference/cwnd-class.md#onlbuttonup) (UINT，CPoint) ;|
|ON_WM_MBUTTONDBLCLK ( # A1|afx_msg void [OnMButtonDblClk](../../mfc/reference/cwnd-class.md#onmbuttondblclk) (UINT，CPoint) ;|
|ON_WM_MBUTTONDOWN ( # A1|afx_msg void [OnMButtonDown](../../mfc/reference/cwnd-class.md#onmbuttondown) (UINT，CPoint) ;|
|ON_WM_MBUTTONUP ( # A1|afx_msg void [OnMButtonUp](../../mfc/reference/cwnd-class.md#onmbuttonup) (UINT，CPoint) ;|
|ON_WM_MDIACTIVATE ( # A1|afx_msg void [OnMDIActivate](../../mfc/reference/cwnd-class.md#onmdiactivate) (BOOL，cwnd \* ，cwnd \*) ;|
|ON_WM_MEASUREITEM ( # A1|afx_msg void [OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) (LPMEASUREITEMSTRUCT) ;|
|ON_WM_MENUCHAR ( # A1|afx_msg LONG [OnMenuChar](../../mfc/reference/cwnd-class.md#onmenuchar) (UINT，Uint，CMenu \*) ;|
|ON_WM_MENUDRAG ( # A1|afx_msg UINT [OnMenuDrag](../../mfc/reference/cwnd-class.md#onmenudrag) (Uint，CMenu \*) ;|
|ON_WM_MENUGETOBJECT ( # A1|afx_msg UINT [OnMenuGetObject](../../mfc/reference/cwnd-class.md#onmenugetobject) (MENUGETOBJECTINFO \*) ;|
|ON_WM_MENURBUTTONUP ( # A1|afx_msg void [OnMenuRButtonUp](../../mfc/reference/cwnd-class.md#onmenurbuttonup) (UINT，CMenu \*) ;|
|ON_WM_MENUSELECT ( # A1|afx_msg void [OnMenuSelect](../../mfc/reference/cwnd-class.md#onmenuselect) (UINT，UINT，HMENU) ;|
|ON_WM_MOUSEACTIVATE ( # A1| ( CWnd [](../../mfc/reference/cwnd-class.md#onmouseactivate) ，UINT， \* uint ) afx_msg int OnMouseActivate;|
|ON_WM_MOUSEHOVER ( # A1|afx_msg void [OnMouseHover](../../mfc/reference/cwnd-class.md#onmousehover) (UINT，CPoint) ;|
|ON_WM_MOUSEHWHEEL ( # A1|afx_msg void [OnMouseHWheel](../../mfc/reference/cwnd-class.md#onmousehwheel) (UINT，Short，CPoint) ;|
|ON_WM_MOUSELEAVE ( # A1|afx_msg void [OnMouseLeave](../../mfc/reference/cwnd-class.md#onmouseleave) ( # A1;|
|ON_WM_MOUSEMOVE ( # A1|afx_msg void [OnMouseMove](../../mfc/reference/cwnd-class.md#onmousemove) ( UINT，CPoint) ;|
|ON_WM_MOUSEWHEEL ( # A1|afx_msg BOOL [OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel) (UINT，Short，CPoint) ;|
|ON_WM_MOVE ( # A1|afx_msg void [OnMove](../../mfc/reference/cwnd-class.md#onmove) (int，int) ;|
|ON_WM_MOVING ( # A1|afx_msg void [OnMoving](../../mfc/reference/cwnd-class.md#onmoving) (UINT，LPRECT) ;|

## <a name="see-also"></a>请参阅

[消息映射](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ 消息的处理程序](../../mfc/reference/handlers-for-wm-messages.md)
