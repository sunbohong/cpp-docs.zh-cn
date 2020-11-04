---
title: RELOG_DESCRIPTOR 结构
description: C++ Build Insights SDK RELOG_DESCRIPTOR 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9b3c870998ce4f9ca55fb5bcc23ba66a1af46558
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922440"
---
# <a name="relog_descriptor-structure"></a>RELOG_DESCRIPTOR 结构

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`RELOG_DESCRIPTOR` 结构与 [RelogA](../functions/relog-a.md) 和 [RelogW](../functions/relog-w.md) 函数结合使用。 本文介绍应如何重新记录 Windows 事件跟踪 (ETW) 跟踪。

## <a name="syntax"></a>语法

```cpp
typedef struct RELOG_DESCRIPTOR_TAG
{
    unsigned                NumberOfAnalysisPasses;
    ANALYSIS_CALLBACKS      AnalysisCallbacks;
    RELOG_CALLBACKS         RelogCallbacks;
    unsigned long long      SystemEventsRetentionFlags;
    void*                   AnalysisContext;
    void*                   RelogContext;
} RELOG_DESCRIPTOR;
```

## <a name="members"></a>成员

| 名称 | 描述 |
|--|--|
| `NumberOfAnalysisPasses` | 在重新记录会话的分析阶段，应通过 ETW 跟踪完成的分析传递的数量。 |
| `AnalysisCallbacks` | 一个 [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 对象，用于指定在重新记录会话的分析阶段要调用的函数。 |
| `RelogCallbacks` | 一个 [RELOG_CALLBACKS](relog-callbacks-struct.md) 对象，用于指定在重新记录会话的重新记录阶段要调用的函数。 |
| `SystemEventsRetentionFlags` | 一个 [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](relog-retention-system-event-flags-constants.md) 位掩码，用于指定哪些系统 ETW 事件要保留在重新记录的跟踪中。 |
| `AnalysisContext` | 一个由用户提供的上下文，作为参数传递给 `AnalysisCallbacks` 中指定的所有回调函数 |
| `RelogContext` | 一个由用户提供的上下文，作为参数传递给 `RelogCallbacks` 中指定的所有回调函数 |

## <a name="remarks"></a>备注

在重新记录会话期间，ETW 事件的重新记录由用户通过 `RelogCallbacks` 中指定的回调函数来控制。 但是，系统 ETW 事件（如 CPU 采样）不会被转发到这些回调函数。 使用 `SystemEventsRetentionFlags` 字段可以控制系统 ETW 事件的重新记录。

`AnalysisCallbacks` 和 `RelogCallbacks` 结构只接受指向非成员函数的指针。 将它们设置为对象指针便可绕过此限制。 此对象指针将作为参数传递给所有非成员回调函数。 使用此指针从非成员回调函数内调用成员函数。

重新记录会话的分析阶段始终在重新记录阶段之前执行。

::: moniker-end
