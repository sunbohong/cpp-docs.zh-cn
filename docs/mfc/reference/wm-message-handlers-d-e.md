---
description: 了解详细信息： WM_ 消息处理程序： D-E
title: WM_ 消息处理程序：D - E
ms.date: 11/04/2016
f1_keywords:
- ON_WM_ERASEBKGND
- ON_WM_DEVICECHANGE
- ON_WM_ENTERIDLE
- ON_WM_DESTROYCLIPBOARD
- ON_WM_DESTROY
- ON_WM_DEADCHAR
- ON_WM_DELETEITEM
- ON_WM_DROPFILES
- ON_WM_DEVMODECHANGE
- ON_WM_ENDSESSION
- ON_WM_ENABLE
- ON_WM_DRAWITEM
- ON_WM_DRAWCLIPBOARD
helpviewer_keywords:
- ON_WM_ENTERIDLE [MFC]
- ON_WM_DESTROYCLIPBOARD [MFC]
- ON_WM_DEADCHAR [MFC]
- ON_WM_DEVMODECHANGE [MFC]
- ON_WM_ERASEBKGND [MFC]
- ON_WM_DESTROY [MFC]
- ON_WM_DRAWCLIPBOARD [MFC]
- ON_WM_ENDSESSION [MFC]
- ON_WM_DRAWITEM [MFC]
- ON_WM_ENABLE [MFC]
- ON_WM_DROPFILES [MFC]
- ON_WM_DELETEITEM [MFC]
- ON_WM_DEVICECHANGE [MFC]
- WM_ messages [MFC]
ms.assetid: 56fb89c8-68a8-4adf-883e-a9f63bf677e9
ms.openlocfilehash: fc9de81127e008eb69a57b39bd66907214b48f89
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218480"
---
# <a name="wm_-message-handlers-d---e"></a>WM_ 消息处理程序：D - E

下面左侧的映射条目对应于右侧的函数原型：

|映射条目|函数原型|
|---------------|------------------------|
|ON_WM_DEADCHAR ( # A1|afx_msg void [OnDeadChar](../../mfc/reference/cwnd-class.md#ondeadchar) (UINT，UINT，uint) ;|
|ON_WM_DELETEITEM ( # A1|afx_msg void [OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) (INT，LPDELETEITEMSTRUCT) ;|
|ON_WM_DESTROY ( # A1|afx_msg void [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) ( # A1;|
|ON_WM_DESTROYCLIPBOARD ( # A1|afx_msg void [OnDestroyClipboard](../../mfc/reference/cwnd-class.md#ondestroyclipboard) ( # A1;|
|ON_WM_DEVICECHANGE ( # A1|afx_msg void [OnDeviceChange](../../mfc/reference/cwnd-class.md#ondevicechange) (UINT，DWORD) ;|
|ON_WM_DEVMODECHANGE ( # A1|afx_msg void [OnDevModeChange](../../mfc/reference/cwnd-class.md#ondevmodechange) (LPSTR) ;|
|ON_WM_DRAWCLIPBOARD ( # A1|afx_msg void [OnDrawClipboard](../../mfc/reference/cwnd-class.md#ondrawclipboard) ( # A1;|
|ON_WM_DRAWITEM ( # A1|afx_msg void [OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) (LPDRAWITEMSTRUCT) ;|
|ON_WM_DROPFILES ( # A1|afx_msg void [OnDropFiles](../../mfc/reference/cwnd-class.md#ondropfiles) (HDROP) ;|
|ON_WM_DWMCOLORIZATIONCOLORCHANGED ( # A1|afx_msg void [OnColorizationColorChanged](../../mfc/reference/cwnd-class.md#oncolorizationcolorchanged) (DWORD，BOOL) ;|
|ON_WM_DWMCOMPOSITIONCHANGED ( # A1|afx_msg void [OnCompositionChanged](../../mfc/reference/cwnd-class.md#oncompositionchanged) ( # A1;|
|ON_WM_DWMNCRENDERINGCHANGED ( # A1|afx_msg void [OnNcRenderingChanged](../../mfc/reference/cwnd-class.md#onncrenderingchanged) (BOOL) ;|
|ON_WM_DWMWINDOWMAXIMIZEDCHANGE ( # A1|afx_msg void [OnWindowMaximizedChanged](../../mfc/reference/cwnd-class.md#onwindowmaximizedchanged) (BOOL) ;|
|ON_WM_ENABLE ( # A1|afx_msg void [OnEnable](../../mfc/reference/cwnd-class.md#onenable) (BOOL) ;|
|ON_WM_ENDSESSION ( # A1|afx_msg void [OnEndSession](../../mfc/reference/cwnd-class.md#onendsession) (BOOL) ;|
|ON_WM_ENTERIDLE ( # A1|afx_msg void [OnEnterIdle](../../mfc/reference/cwnd-class.md#onenteridle) (UINT，CWnd * ) ;|
|ON_WM_ENTERSIZEMOVE ( # A1|afx_msg void [OnEnterSizeMove](../../mfc/reference/cwnd-class.md#onentersizemove) ( # A1;|
|ON_WM_ERASEBKGND ( # A1|[ (CDC](../../mfc/reference/cwnd-class.md#onerasebkgnd) * ) AFX_MSG BOOL *;|
|ON_WM_EXITSIZEMOVE ( # A1|afx_msg void [OnExitSizeMove](../../mfc/reference/cwnd-class.md#onexitsizemove) ( # A1;|

## <a name="see-also"></a>请参阅

[消息映射](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ 消息的处理程序](../../mfc/reference/handlers-for-wm-messages.md)
