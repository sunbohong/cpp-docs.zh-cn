---
title: StopAndRelogTracingSession
description: C++ Build Insights SDK StopAndRelogTracingSession 函数引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d36dee1b16ca467d16b22587abe3ef34ee6ccb29
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919951"
---
# <a name="stopandrelogtracingsession"></a>StopAndRelogTracingSession

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndRelogTracingSession` 函数用于停止正在进行的跟踪会话并将生成的跟踪保存在临时文件中。 然后，将临时文件用作输入来立即启动重新记录会话。 重新记录会话生成的最终重新记录跟踪保存在由调用方指定的文件中。 调用此函数的可执行文件必须具有管理员权限。

## <a name="syntax"></a>语法

```cpp
template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE StopAndRelogTracingSession(
    const char*                                   sessionName,
    const char*                                   outputLogFile,
    TRACING_SESSION_STATISTICS*                   statistics,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);

template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE StopAndRelogTracingSession(
    const wchar_t*                                sessionName,
    const wchar_t*                                outputLogFile,
    TRACING_SESSION_STATISTICS*                   statistics,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);
```

### <a name="parameters"></a>参数

sessionName\
要停止的跟踪会话的名称。 使用传递给 [StartTracingSession](start-tracing-session.md)、[StartTracingSessionA](start-tracing-session-a.md) 或 [StartTracingSessionW](start-tracing-session-w.md) 的相同会话名称。

outputLogFile\
要在其中写入由重新记录会话生成的重新记录跟踪的文件。

statistics\
指向 [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) 对象的指针。 `StopAndRelogTracingSession` 在返回之前写入此对象中的跟踪集合统计信息。

numberOfAnalysisPasses\
要在跟踪上运行的分析传递数。 每个分析传递通过提供的分析器组传递一次跟踪。

systemEventsRetentionFlags\
一个 [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md) 位掩码，用于指定哪些系统 ETW 事件要保留在重新记录的跟踪中。

analyzerGroup\
用于重新记录会话的分析阶段的分析器组。 调用 [MakeStaticAnalyzerGroup](make-static-analyzer-group.md) 以创建分析器组。 若要使用从 [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md) 中获取的动态分析器组，请先通过将其地址传递给 `MakeStaticAnalyzerGroup` 来将该组封装在静态分析器组内。

reloggerGroup\
将事件重新记录到 outputLogFile 中指定的跟踪文件中的重新记录器组。 调用 [MakeStaticReloggerGroup](make-static-relogger-group.md) 以创建重新记录器组。 若要使用从 [MakeDynamicReloggerGroup](make-dynamic-relogger-group.md) 中获取的动态重新记录器组，请先通过将其地址传递给 `MakeStaticReloggerGroup` 来将该组封装在静态重新记录器组内。

### <a name="return-value"></a>返回值

[RESULT_CODE](../other-types/result-code-enum.md) 枚举中的结果代码。

### <a name="remarks"></a>注解

输入跟踪通过分析器组传递 *numberOfAnalysisPasses* 次。 重新记录传递没有类似的选项。 在所有分析传递完成后，通过重新记录器组只会传递一次跟踪。

不支持重新记录来自重新记录器类中的系统事件（如 CPU 示例）。 使用 systemEventsRetentionFlags 参数确定要保留在输出跟踪中的系统事件。

::: moniker-end
