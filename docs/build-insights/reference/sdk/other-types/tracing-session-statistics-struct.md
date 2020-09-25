---
title: TRACING_SESSION_STATISTICS 结构
description: 了解 C++ Build Insights SDK TRACING_SESSION_STATISTICS 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_STATISTICS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c1db302d9e816591624f0fc63633351d32684097
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742757"
---
# <a name="tracing_session_statistics-structure"></a>TRACING_SESSION_STATISTICS 结构

::: moniker range="<=vs-2015"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=vs-2017"

`TRACING_SESSION_STATISTICS` 结构描述了所收集跟踪的统计信息。 在停止跟踪会话时设置字段。

## <a name="syntax"></a>语法

```cpp
typedef struct TRACING_SESSION_STATISTICS_TAG
{
    unsigned long MSVCEventsLost;
    unsigned long MSVCBuffersLost;
    unsigned long SystemEventsLost;
    unsigned long SystemBuffersLost;

} TRACING_SESSION_STATISTICS;
```

## <a name="members"></a>成员

| 名称 | 描述 |
|--|--|
| `MSVCEventsLost` | 已删除的 MSVC 事件数。 |
| `MSVCBuffersLost` | 已删除的 MSVC 事件缓冲区数。 |
| `SystemEventsLost` | 已删除的系统事件数。 |
| `SystemBuffersLost` | 已删除的系统事件缓冲区数。 |

## <a name="remarks"></a>备注

在调用以下函数时，将填充此结构：

- [StopTracingSession](../functions/stop-tracing-session.md)
- [StopTracingSessionA](../functions/stop-tracing-session-a.md)
- [StopTracingSessionW](../functions/stop-tracing-session-w.md)
- [StopAndAnalyzeTracingSession](../functions/stop-and-analyze-tracing-session.md)
- [StopAndAnalyzeTracingSessionA](../functions/stop-and-analyze-tracing-session-a.md)
- [StopAndAnalyzeTracingSessionW](../functions/stop-and-analyze-tracing-session-w.md)
- [StopAndRelogTracingSession](../functions/stop-and-relog-tracing-session.md)
- [StopAndRelogTracingSessionA](../functions/stop-and-relog-tracing-session-a.md)
- [StopAndRelogTracingSessionW](../functions/stop-and-relog-tracing-session-w.md)

::: moniker-end
