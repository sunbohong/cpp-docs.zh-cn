---
title: InjectEvent
description: C++ Build Insights SDK InjectEvent 函数引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InjectEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b4d85f17a6d553d9dffa727824e6d4de94518645
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922842"
---
# <a name="injectevent"></a>InjectEvent

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`InjectEvent` 函数是在实现 [IRelogger](../other-types/irelogger-class.md) 接口的重新记录器中调用的。 它用于在重新记录会话的输出跟踪文件中写入 Windows 事件跟踪 (ETW) 事件。

## <a name="syntax"></a>语法

```cpp
void InjectEvent(
    const void* relogSession,
    LPCGUID providerId,
    PCEVENT_DESCRIPTOR eventDescriptor,
    unsigned long processId,
    unsigned long threadId,
    unsigned short processorIndex,
    long long timestamp,
    unsigned char* data,
    unsigned long byteCount);
```

### <a name="parameters"></a>参数

relogSession\
指向重新记录会话的指针。 为实现 `IRelogger` 接口的重新记录器提供了重新记录会话。 有关详细信息，请参阅 [IRelogger](../other-types/irelogger-class.md)。

providerId\
用于重新记录 ETW 事件的 Windows 事件跟踪 (ETW) 提供程序 GUID。

eventDescriptor\
已重新记录的 ETW 事件的 ETW 事件描述符。

processId\
已重新记录的 ETW 事件的进程标识符 (PID)。

threadId\
已重新记录的 ETW 事件的线程标识符 (TID)。

processorIndex\
已重新记录的 ETW 事件的处理器索引。

timestamp\
已重新记录的 ETW 事件的时间戳。

data\
指向应包含在已重新记录的 ETW 事件中的数据的指针。

byteCount\
由 data 指向的数据的大小（以字节为单位）。

## <a name="remarks"></a>备注

有关 ETW 概念的详细信息（如“提供程序 GUID”和“事件描述符”，请参阅 [ETW 文档](/windows/win32/etw/about-event-tracing)。 有关如何使用 C++ Build Insights SDK 启动重新记录会话的详细信息，请参阅[重新记录](relog.md)。

::: moniker-end
