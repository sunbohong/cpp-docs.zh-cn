---
description: 了解详细信息： MessageHandler
title: MessageHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
ms.openlocfilehash: d369b94721e57eb4adc704570bc09d1aae184fe1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159500"
---
# <a name="messagehandler"></a>MessageHandler

`MessageHandler` 由消息映射中 MESSAGE_HANDLER 宏的第二个参数标识的函数的名称。

## <a name="syntax"></a>语法

```cpp
LRESULT MessageHandler(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>parameters

*uMsg*<br/>
指定消息。

*wParam*<br/>
其他的消息特定信息。

*lParam*<br/>
其他的消息特定信息。

*bHandled*<br/>
消息映射在调用之前将 *bHandled* 设置为 TRUE `MessageHandler` 。 如果 `MessageHandler` 未完全处理消息，则应将 *bHandled* 设置为 FALSE，以指示消息需要进一步处理。

## <a name="return-value"></a>返回值

消息处理的结果。 如果成功，则为0。

## <a name="remarks"></a>备注

有关在消息映射中使用此消息处理程序的示例，请参阅 [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler)。

## <a name="see-also"></a>请参阅

[实现窗口](../atl/implementing-a-window.md)<br/>
[消息映射](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
