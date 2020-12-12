---
description: 了解详细信息： WM_ 消息处理程序： A-C
title: WM_ 消息处理程序：A - C
ms.date: 11/04/2016
f1_keywords:
- ON_WM_CREATE
- ON_WM_COMPACTING
- ON_WM_CHARTOITEM
- ON_WM_ASKCBFORMATNAME
- ON_WM_CTLCOLOR
- ON_WM_COMPAREITEM
- ON_WM_CHILDACTIVATE
- ON_WM_CONTEXTMENU
- ON_WM_ACTIVATE
- ON_WM_CANCELMODE
- ON_WM_CLOSE
- ON_WM_CAPTURECHANGED
- ON_WM_ACTIVATEAPP
- ON_WM_CHAR
- ON_WM_CHANGECBCHAIN
helpviewer_keywords:
- ON_WM_COMPACTING [MFC]
- ON_WM_COMPAREITEM [MFC]
- ON_WM_CLOSE [MFC]
- ON_WM_CTLCOLOR [MFC]
- ON_WM_CHAR [MFC]
- ON_WM_CAPTURECHANGED [MFC]
- ON_WM_CHARTOITEM [MFC]
- ON_WM_CREATE [MFC]
- ON_WM_ACTIVATE [MFC]
- ON_WM_CONTEXTMENU [MFC]
- ON_WM_CANCELMODE [MFC]
- ON_WM_ASKCBFORMATNAME [MFC]
- ON_WM_CHILDACTIVATE [MFC]
- WM_ messages [MFC]
- ON_WM_ACTIVATEAPP [MFC]
- ON_WM_CHANGECBCHAIN
ms.assetid: 4e315896-d646-4b87-b0ab-41a4a753b045
ms.openlocfilehash: 898635961e3fc1ad3df571e813bcfef629318446
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218441"
---
# <a name="wm_-message-handlers-a---c"></a>WM_ 消息处理程序：A - C

下面左侧的映射条目对应于右侧的函数原型：

|映射条目|函数原型|
|---------------|------------------------|
|ON_WM_ACTIVATE ( # A1|afx_msg void [OnActivate](../../mfc/reference/cwnd-class.md#onactivate) (UINT，CWnd \* ，BOOL) ;|
|ON_WM_ACTIVATEAPP ( # A1|afx_msg void [OnActivateApp](../../mfc/reference/cwnd-class.md#onactivateapp) (BOOL、DWORD) ;|
|ON_WM_APPCOMMAND ( # A1|afx_msg void [OnAppCommand](../../mfc/reference/cwnd-class.md#onappcommand) (CWnd \* ，uint，uint，uint) ;|
|ON_WM_ASKCBFORMATNAME ( # A1|afx_msg void [OnAskCbFormatName](../../mfc/reference/cwnd-class.md#onaskcbformatname) (UINT，LPSTR) ;|
|ON_WM_CANCELMODE ( # A1|afx_msg void [OnCancelMode](../../mfc/reference/cwnd-class.md#oncancelmode) ( # A1;|
|ON_WM_CAPTURECHANGED ( # A1|afx_msg void [OnCaptureChanged](../../mfc/reference/cwnd-class.md#oncapturechanged) (CWnd \*) ;|
|ON_WM_CHANGECBCHAIN ( # A1|afx_msg void [OnChangeCbChain](../../mfc/reference/cwnd-class.md#onchangecbchain) (HWND，hwnd) ;|
|ON_WM_CHAR ( # A1|afx_msg void [OnChar](../../mfc/reference/cwnd-class.md#onchar) (UINT，UINT，uint) ;|
|ON_WM_CHARTOITEM ( # A1|afx_msg int [OnCharToItem](../../mfc/reference/cwnd-class.md#onchartoitem) (UINT，CWnd \* ，UINT) ;|
|ON_WM_CHILDACTIVATE ( # A1|afx_msg void [OnChildActivate](../../mfc/reference/cwnd-class.md#onchildactivate) ( # A1;|
|ON_WM_CLIPBOARDUPDATE ( # A1|afx_msg void [OnClipboardUpdate](../../mfc/reference/cwnd-class.md#onclipboardupdate) ( # A1;|
|ON_WM_CLOSE ( # A1|afx_msg void [OnClose](../../mfc/reference/cwnd-class.md#onclose) ( # A1;|
|ON_WM_COMPACTING ( # A1|afx_msg void [OnCompacting](../../mfc/reference/cwnd-class.md#oncompacting) (UINT) ;|
|ON_WM_COMPAREITEM ( # A1|afx_msg int [OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) (LPCOMPAREITEMSTRUCT) ;|
|ON_WM_CONTEXTMENU ( # A1| (CWnd [](../../mfc/reference/cwnd-class.md#oncontextmenu) Afx_msg void OnContextMenu \* ，CPoint) ;|
|ON_WM_COPYDATA ( # A1|afx_msg ([CWnd](../../mfc/reference/cwnd-class.md#oncopydata) \* pWnd，COPYDATASTRUCT \* pCopyDataStruct) ;|
|ON_WM_CREATE ( # A1|afx_msg int [OnCreate](../../mfc/reference/cwnd-class.md#oncreate) (LPCREATESTRUCT) ;|
|ON_WM_CTLCOLOR ( # A1|afx_msg HBRUSH [OnCtlColor](../../mfc/reference/cwnd-class.md#onctlcolor) (CDC \* ，CWnd \* ，UINT) ;|

## <a name="see-also"></a>请参阅

[消息映射](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ 消息的处理程序](../../mfc/reference/handlers-for-wm-messages.md)
