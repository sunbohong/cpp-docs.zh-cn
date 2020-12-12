---
description: 了解详细信息： WM_ 消息： P-R
title: WM_ 消息：P - R
ms.date: 11/04/2016
f1_keywords:
- ON_WM_RBUTTONUP
- ON_WM_PALETTECHANGED
- ON_WM_RBUTTONDBLCLK
- ON_WM_QUERYENDSESSION
- ON_WM_PARENTNOTIFY
- ON_WM_PALETTEISCHANGING
- ON_WM_QUERYOPEN
- ON_WM_PAINT
- ON_WM_QUERYNEWPALETTE
- ON_WM_RBUTTONDOWN
- ON_WM_RENDERALLFORMATS
- ON_WM_PAINTCLIPBOARD
- ON_WM_RENDERFORMAT
- ON_WM_QUERYDRAGICON
helpviewer_keywords:
- ON_WM_RENDERFORMAT [MFC]
- ON_WM_QUERYOPEN [MFC]
- ON_WM_RBUTTONDOWN [MFC]
- ON_WM_PAINTCLIPBOARD [MFC]
- ON_WM_QUERYNEWPALETTE [MFC]
- ON_WM_RBUTTONUP [MFC]
- ON_WM_PARENTNOTIFY [MFC]
- ON_WM_RBUTTONDBLCLK [MFC]
- ON_WM_PALETTECHANGED [MFC]
- ON_WM_PALETTEISCHANGING [MFC]
- ON_WM_QUERYDRAGICON [MFC]
- ON_WM_PAINT [MFC]
- ON_WM_RENDERALLFORMATS [MFC]
- ON_WM_QUERYENDSESSION [MFC]
- WM_ messages
ms.assetid: f46962e5-8329-4f1f-9b4d-fdad2a5ce1f8
ms.openlocfilehash: d1e3ad4ca65bcf9f4b1b0901a6fe1dbf441595e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218298"
---
# <a name="wm_-messages-p---r"></a>WM_ 消息：P - R

以下映射条目对应于函数原型：

|映射条目|函数原型|
|---------------|------------------------|
|ON_WM_PAINT ( # A1|afx_msg void [OnPaint](../../mfc/reference/cwnd-class.md#onpaint) ( # A1;|
|ON_WM_PAINTCLIPBOARD ( # A1|afx_msg void [OnPaintClipboard](../../mfc/reference/cwnd-class.md#onpaintclipboard) ( CWnd *，处理 ) ;|
|ON_WM_PALETTECHANGED ( # A1|afx_msg void [OnPaletteChanged](../../mfc/reference/cwnd-class.md#onpalettechanged) ( CWnd * ) ;|
|ON_WM_PALETTEISCHANGING ( # A1|afx_msg void [OnPaletteIsChanging](../../mfc/reference/cwnd-class.md#onpaletteischanging) ( CWnd * ) ;|
|ON_WM_PARENTNOTIFY ( # A1|afx_msg void [OnParentNotify](../../mfc/reference/cwnd-class.md#onparentnotify) ( UINT，LONG ) ;|
|ON_WM_POWERBROADCAST ( # A1|afx_msg UINT [onpowerbroadcast 签名](../../mfc/reference/cwnd-class.md#onpowerbroadcast) ( UINT，uint ) ;|
|ON_WM_QUERYDRAGICON ( # A1|afx_msg HCURSOR [OnQueryDragIcon](../../mfc/reference/cwnd-class.md#onquerydragicon) ( # A1 # A2 # A3;|
|ON_WM_QUERYENDSESSION ( # A1|afx_msg BOOL [OnQueryEndSession](../../mfc/reference/cwnd-class.md#onqueryendsession) ( # A1 # A2 # A3;|
|ON_WM_QUERYNEWPALETTE ( # A1|afx_msg BOOL [OnQueryNewPalette](../../mfc/reference/cwnd-class.md#onquerynewpalette) ( # A1 # A2 # A3;|
|ON_WM_QUERYOPEN ( # A1|afx_msg BOOL [OnQueryOpen](../../mfc/reference/cwnd-class.md#onqueryopen) ( # A1 # A2 # A3;|
|ON_WM_RBUTTONDBLCLK ( # A1|afx_msg void [OnRButtonDblClk](../../mfc/reference/cwnd-class.md#onrbuttondblclk) ( UINT，CPoint ) ;|
|ON_WM_RBUTTONDOWN ( # A1|afx_msg void [OnRButtonDown](../../mfc/reference/cwnd-class.md#onrbuttondown) ( UINT，CPoint ) ;|
|ON_WM_RBUTTONUP ( # A1|afx_msg void [OnRButtonUp](../../mfc/reference/cwnd-class.md#onrbuttonup) ( UINT，CPoint ) ;|
|ON_WM_RENDERALLFORMATS ( # A1|afx_msg void [OnRenderAllFormats](../../mfc/reference/cwnd-class.md#onrenderallformats) ( # A1;|
|ON_WM_RENDERFORMAT ( # A1|afx_msg void [OnRenderFormat](../../mfc/reference/cwnd-class.md#onrenderformat) ( UINT ) ;|

## <a name="see-also"></a>请参阅

[消息映射](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ 消息的处理程序](../../mfc/reference/handlers-for-wm-messages.md)
