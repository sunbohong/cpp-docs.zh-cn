---
title: StopAndAnalyzeTracingSession
description: C++ Build Insights SDK StopAndAnalyzeTracingSession 函数引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 81a8ce43ecedfa51874508193637969411ae52d6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922717"
---
# <a name="stopandanalyzetracingsession"></a>StopAndAnalyzeTracingSession

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndAnalyzeTracingSession` 函数用于停止正在进行的跟踪会话并将生成的跟踪保存在临时文件中。 然后，使用临时文件作为输入立即启动分析会话。 调用此函数的可执行文件必须具有管理员权限。

## <a name="syntax"></a>语法

```cpp
template <typename... TAnalyzerGroupMembers>
RESULT_CODE StopAndAnalyzeTracingSession(
    const char*                                   sessionName,
    unsigned                                      numberOfAnalysisPasses,
    TRACING_SESSION_STATISTICS*                   statistics,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);

template <typename... TAnalyzerGroupMembers>
RESULT_CODE StopAndAnalyzeTracingSession(
    const wchar_t*                                sessionName,
    unsigned                                      numberOfAnalysisPasses,
    TRACING_SESSION_STATISTICS*                   statistics,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);
```

### <a name="parameters"></a>参数

sessionName\
要停止的跟踪会话的名称。 使用传递给 [StartTracingSession](start-tracing-session.md)、[StartTracingSessionA](start-tracing-session-a.md) 或 [StartTracingSessionW](start-tracing-session-w.md) 的相同会话名称。

numberOfAnalysisPasses\
要在跟踪上运行的分析传递数。 每个分析传递通过提供的分析器组传递一次跟踪。

statistics\
指向 [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) 对象的指针。 `StopAndAnalyzeTracingSession` 在返回之前写入此对象中的跟踪集合统计信息。

analyzerGroup\
用于分析的分析器组。 调用 [MakeStaticAnalyzerGroup](make-static-analyzer-group.md) 以创建分析器组。 若要使用从 [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md) 中获取的动态分析器组，请先通过将其地址传递给 `MakeStaticAnalyzerGroup` 来将该组封装在静态分析器组内。

### <a name="return-value"></a>返回值

[RESULT_CODE](../other-types/result-code-enum.md) 枚举中的结果代码。

::: moniker-end
