---
title: ANALYSIS_CALLBACKS 结构
description: C++ Build Insights SDK ANALYSIS_CALLBACKS 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3fae97370ff9366ffc2fbd8d046a73c30125e554
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919925"
---
# <a name="analysis_callbacks-structure"></a>ANALYSIS_CALLBACKS 结构

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

在初始化 [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) 或 [RELOG_DESCRIPTOR](relog-descriptor-struct.md) 对象时会使用 `ANALYSIS_CALLBACKS` 结构。 它指定了在分析或重新记录一个 Windows 事件跟踪 (ETW) 跟踪过程中要调用的函数。

## <a name="syntax"></a>语法

```cpp
typedef struct ANALYSIS_CALLBACKS_TAG
{
    OnAnalysisEventFunc     OnStartActivity;
    OnAnalysisEventFunc     OnStopActivity;
    OnAnalysisEventFunc     OnSimpleEvent;
    OnTraceInfoFunc         OnTraceInfo;
    OnBeginEndPassFunc      OnBeginAnalysis;
    OnBeginEndPassFunc      OnEndAnalysis;
    OnBeginEndPassFunc      OnBeginAnalysisPass;
    OnBeginEndPassFunc      OnEndAnalysisPass;
} ANALYSIS_CALLBACKS;
```

## <a name="members"></a>成员

| 名称 | 描述 |
|--|--|
| `OnStartActivity` | 调用以处理活动开始事件。 |
| `OnStopActivity` | 调用以处理活动停止事件。 |
| `OnSimpleEvent` | 调用以处理简单事件。 |
| `OnTraceInfo` | 对于分析会话，在每个分析传递开始时调用。 对于重新记录会话，在每个分析传递开始时调用，并在重新记录传递开始时再次调用。 只有在调用 OnBeginAnalysisPass 后，才会调用此函数。 |
| `OnBeginAnalysis` | 对于分析会话，在任何分析传递开始之前调用。 对于重新记录会话，在分析阶段开始之前调用两次：一次是宣布启动重新记录会话，另一次是宣布分析阶段开始。 |
| `OnEndAnalysis` | 对于分析会话，在所有分析传递结束后调用此函数。 对于重新记录会话，在分析阶段的所有分析传递结束后调用此函数。 然后，在重新记录传递结束后再次调用它。 |
| `OnBeginAnalysisPass` | 在开始分析传递或重新记录传递时，在处理任何事件之前调用。 |
| `OnEndAnalysisPass` | 在结束分析传递或重新记录传递时，在处理所有事件之后调用。 |

## <a name="remarks"></a>备注

重新记录会话的分析阶段被视为重新记录会话的一部分，可能包含多个分析传递。 出于此原因，在重新记录会话开始时连续调用两次 `OnBeginAnalysis`。 在分析阶段结束时，在开始重新记录阶段之前调用 `OnEndAnalysis`，并在重新记录阶段结束时再次调用它。 重新记录阶段始终包含一个重新记录传递。

可以将分析器作为重新记录会话的分析和重新记录阶段的一部分。 这些分析器可以通过跟踪 OnBeginAnalysis 和 `OnEndAnalysis` 调用对来确定当前所处的阶段。 两个 `OnBeginAnalysis` 调用而无任何 `OnEndAnalysis` 调用表示分析阶段正在进行。 两个 `OnBeginAnalysis` 调用和一个 `OnEndAnalysis` 调用表示重新记录阶段正在进行。 两个 OnBeginAnalysis 和两个 `OnEndAnalysis` 调用表示两个阶段都已结束。

`ANALYSIS_CALLBACKS` 结构的所有成员都必须指向一个有效的函数。 有关接受的函数签名的详细信息，请参阅 [OnAnalysisEventFunc](on-analysis-event-func-typedef.md)、[OnTraceInfoFunc](on-trace-info-func-typedef.md) 和 [OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md)。

::: moniker-end
