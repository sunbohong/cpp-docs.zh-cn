---
title: TRACE_INFO_DATA 结构
description: C++ Build Insights SDK TRACE_INFO_DATA 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACE_INFO_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ce6301b168aed9f279fc7aaee9aa3a97221fd23a
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923426"
---
# <a name="trace_info_data-structure"></a>TRACE_INFO_DATA 结构

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`TRACE_INFO_DATA` 结构描述要分析或重新记录的跟踪。

## <a name="syntax"></a>语法

```cpp
typedef struct TRACE_INFO_DATA_TAG
{
    unsigned long           LogicalProcessorCount;
    long long               TickFrequency;
    long long               StartTimestamp;
    long long               StopTimestamp;

} TRACE_INFO_DATA;
```

## <a name="members"></a>成员

| 名称 | 说明 |
|--|--|
| `LogicalProcessorCount` | 收集跟踪的计算机上的逻辑处理器数。 |
| `TickFrequency` | 在计算持续时间（以“滴答”为计量单位）时使用的每秒滴答数。 |
| `StartTimestamp` | 此字段设置为在启动跟踪时捕获的滴答值。 |
| `StopTimestamp` | 此字段设置为在停止跟踪时捕获的滴答值。 |

## <a name="remarks"></a>备注

从 `StopTimestamp` 中减去 `StartTimestamp` 以获取整个跟踪期间使用的滴答数。 使用 `TickFrequency` 将生成的值转换为时间单位。 有关将滴答数转换为时间单位的示例，请参阅 [EVENT_DATA](event-data-struct.md)。

::: moniker-end
