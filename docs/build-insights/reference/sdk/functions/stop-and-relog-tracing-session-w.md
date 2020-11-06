---
title: StopAndRelogTracingSessionW
description: C++ Build Insights SDK StopAndRelogTracingSessionW 函数引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9c39607b9d088be18fb24238428512be09d78c53
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922682"
---
# <a name="stopandrelogtracingsessionw"></a>StopAndRelogTracingSessionW

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`StopAndRelogTracingSessionW` 函数用于停止正在进行的跟踪会话并将生成的跟踪保存在临时文件中。 然后，将临时文件用作输入来立即启动重新记录会话。 重新记录会话生成的最终重新记录跟踪保存在由调用方指定的文件中。 调用此函数的可执行文件必须具有管理员权限。

## <a name="syntax"></a>语法

```cpp
enum RESULT_CODE StopAndRelogTracingSessionW(
    const wchar_t*              sessionName,
    const wchar_t*              outputLogFile,
    TRACING_SESSION_STATISTICS* statistics,
    const RELOG_DESCRIPTOR*     relogDescriptor);
```

### <a name="parameters"></a>参数

sessionName\
要停止的跟踪会话的名称。 使用传递给 [StartTracingSession](start-tracing-session.md)、[StartTracingSessionA](start-tracing-session-a.md) 或 [StartTracingSessionW](start-tracing-session-w.md) 的相同会话名称。

outputLogFile\
要在其中写入由重新记录会话生成的重新记录跟踪的文件。

statistics\
指向 [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) 对象的指针。 `StopAndRelogTracingSessionW` 在返回之前写入此对象中的跟踪集合统计信息。

analysisDescriptor\
指向 [RELOG_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) 对象的指针。 使用此对象配置 `StopAndRelogTracingSessionW` 启动的重新记录会话。

### <a name="return-value"></a>返回值

[RESULT_CODE](../other-types/result-code-enum.md) 枚举中的结果代码。

::: moniker-end
