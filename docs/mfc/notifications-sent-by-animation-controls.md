---
description: 了解详细信息：动画控件发送的通知
title: 动画控件发送的通知
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], animation controls
- CAnimateCtrl class [MFC], notifications
- controls [MFC], animation
- animation controls [MFC], notifications
ms.assetid: 584f5824-446b-4a1a-85f7-ef61842c8186
ms.openlocfilehash: 17dbd041e1c22b8d6542e64fd8b99d86389ea2d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280555"
---
# <a name="notifications-sent-by-animation-controls"></a>动画控件发送的通知

动画控件 ([CAnimateCtrl](reference/canimatectrl-class.md)) 发送两种不同类型的通知消息。 将以 [WM_COMMAND](/windows/win32/menurc/wm-command) 消息的形式发送通知。

当动画控件开始播放剪辑时，将发送 [ACN_START](/windows/win32/Controls/acn-start) 消息。 当动画控件完成或停止播放剪辑时，将发送 [ACN_STOP](/windows/win32/Controls/acn-stop) 消息。

## <a name="see-also"></a>请参阅

[使用 CAnimateCtrl](using-canimatectrl.md)<br/>
[控件](controls-mfc.md)
