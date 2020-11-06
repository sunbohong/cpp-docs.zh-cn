---
title: StopTracingSessionA
description: C++ Build Insights SDK StopTracingSessionA 函数引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 211538c1756d41b91dab6d43f33f4b4a41ceb70c
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922644"
---
# <a name="stoptracingsessiona"></a>StopTracingSessionA

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`StopTracingSessionA` 函数用于停止正在进行的跟踪会话并生成原始跟踪文件。 可以将原始跟踪文件传递给 [Analyze](analyze.md)、[AnalzeA](analyze-a.md) 和 [AnalyzeW](analyze-w.md) 函数来启动分析会话。 还可以将原始跟踪文件传递给 [Relog](relog.md)、[RelogA](relog-a.md) 和 [RelogW](relog-w.md) 函数来启动重新记录会话。 调用 `StopTracingSessionA` 的可执行文件必须具有管理员权限。

## <a name="syntax"></a>语法

```cpp
enum RESULT_CODE StopTracingSessionA(
    const char*                 sessionName,
    const char*                 outputLogFile,
    TRACING_SESSION_STATISTICS* statistics);
```

### <a name="parameters"></a>参数

sessionName\
要停止的跟踪会话的名称。 使用传递给 [StartTracingSession](start-tracing-session.md)、[StartTracingSessionA](start-tracing-session-a.md) 或 [StartTracingSessionW](start-tracing-session-w.md) 的相同会话名称。

outputLogFile\
应在其中保存原始跟踪的最终输出日志文件的路径。

statistics\
指向 [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) 对象的指针。 `StopTracingSessionA` 在返回之前写入此对象中的跟踪集合统计信息。

### <a name="return-value"></a>返回值

[RESULT_CODE](../other-types/result-code-enum.md) 枚举中的结果代码。

::: moniker-end
