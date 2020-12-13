---
description: 了解详细信息： CommandHandler
title: CommandHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
ms.openlocfilehash: 746048dd83088cac8316cf6e0140644956c21b4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153276"
---
# <a name="commandhandler"></a>CommandHandler

`CommandHandler` 由消息映射中 COMMAND_HANDLER 宏的第三个参数标识的函数。

## <a name="syntax"></a>语法

```cpp
LRESULT CommandHandler(
    WORD wNotifyCode,
    WORD wID,
    HWND hWndCtl,
    BOOL& bHandled);
```

#### <a name="parameters"></a>parameters

*此接通 wnotifycode*<br/>
通知代码。

*wID*<br/>
菜单项、控件或快捷键的标识符。

*hWndCtl*<br/>
窗口控件的句柄。

*bHandled*<br/>
消息映射在调用之前将 *bHandled* 设置为 TRUE `CommandHandler` 。 如果 `CommandHandler` 未完全处理消息，则应将 *bHandled* 设置为 FALSE，以指示消息需要进一步处理。

## <a name="return-value"></a>返回值

消息处理的结果。 如果成功，则为0。

## <a name="remarks"></a>备注

有关在消息映射中使用此消息处理程序的示例，请参阅 [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler)。

## <a name="see-also"></a>请参阅

[实现窗口](../atl/implementing-a-window.md)<br/>
[消息映射](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
