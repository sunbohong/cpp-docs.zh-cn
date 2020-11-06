---
title: StopAndAnalyzeTracingSessionA
description: C++ Build Insights SDK StopAndAnalyzeTracingSessionA 函数引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: fa5adfca2c5e4d3d4bd17abae4e78c2ac6464773
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922731"
---
# <a name="stopandanalyzetracingsessiona"></a>StopAndAnalyzeTracingSessionA

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndAnalyzeTracingSessionA` 函数用于停止正在进行的跟踪会话并将生成的跟踪保存在临时文件中。 然后，使用临时文件作为输入立即启动分析会话。 调用此函数的可执行文件必须具有管理员权限。

## <a name="syntax"></a>语法

```cpp
enum RESULT_CODE StopAndAnalyzeTracingSessionA(
    const char*                 sessionName,
    TRACING_SESSION_STATISTICS* statistics,
    const ANALYSIS_DESCRIPTOR*  analysisDescriptor);
```

### <a name="parameters"></a>参数

sessionName\
要停止的跟踪会话的名称。 使用传递给 [StartTracingSession](start-tracing-session.md)、[StartTracingSessionA](start-tracing-session-a.md) 或 [StartTracingSessionW](start-tracing-session-w.md) 的相同会话名称。

statistics\
指向 [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) 对象的指针。 `StopAndAnalyzeTracingSessionA` 在返回之前写入此对象中的跟踪集合统计信息。

analysisDescriptor\
指向 [ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) 对象的指针。 使用此对象配置 `StopAndAnalyzeTracingSessionA` 启动的分析会话。

### <a name="return-value"></a>返回值

[RESULT_CODE](../other-types/result-code-enum.md) 枚举中的结果代码。

::: moniker-end
