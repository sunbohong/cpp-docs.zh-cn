---
description: 了解详细信息： Thread-Specific 热键
title: 线程特定的热键
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
ms.openlocfilehash: 352d39b801d7e6dcecfbf27d841d6977d3666138
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216114"
---
# <a name="thread-specific-hot-keys"></a>线程特定的热键

应用程序使用 Windows 函数设置线程特定的热键 ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) `RegisterHotKey` 。 当用户按线程特定的热键时，Windows 会将 [WM_HOTKEY](/windows/win32/inputdev/wm-hotkey) 消息发布到特定线程的消息队列的开头。 WM_HOTKEY 消息包含按下的特定热键的虚拟键代码、移位状态和用户定义的 ID。 有关标准虚拟键代码的列表，请参阅 Winuser.h。 有关此方法的详细信息，请参阅 [RegisterHotKey](/windows/win32/api/winuser/nf-winuser-registerhotkey)。

请注意，在调用中使用的移位状态标志与 `RegisterHotKey` [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) 成员函数返回的状态标志不同; 在调用之前，必须转换这些标志 `RegisterHotKey` 。

## <a name="see-also"></a>请参阅

[使用 CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[控件](../mfc/controls-mfc.md)
