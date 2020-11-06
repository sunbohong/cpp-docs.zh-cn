---
title: TraceInfo 类
description: C++ Build Insights SDK TraceInfo 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TraceInfo
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b772cc13981720c73238e56a561ca92144775cb4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922917"
---
# <a name="traceinfo-class"></a>TraceInfo 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`TraceInfo` 类用于访问有关正在分析或重新记录的跟踪的有用属性。

## <a name="syntax"></a>语法

```cpp
class TraceInfo
{
public:
    TraceInfo(const TRACE_INFO_DATA& data);

    const unsigned long& LogicalProcessorCount() const;

    const long long& TickFrequency() const;
    const long long& StartTimestamp() const;
    const long long& StopTimestamp() const;

    std::chrono::nanoseconds Duration() const;
};
```

## <a name="remarks"></a>备注

从 `StopTimestamp` 中减去 `StartTimestamp` 以获取整个跟踪期间使用的滴答数。 使用 `TickFrequency` 将生成的值转换为时间单位。 有关将滴答数转换为时间的示例，请参阅 [EVENT_DATA](../c-event-data-types/event-data-struct.md)。

如果你不想自行转换滴答数，则 `TraceInfo` 类将提供返回跟踪持续时间（以纳秒为单位）的成员函数。 使用标准 C++ `chrono` 库将此值转换为其他时间单位。

## <a name="members"></a>成员

### <a name="constructors"></a>构造函数

[TraceInfo](#trace-info)

### <a name="functions"></a>函数

[Duration](#duration)
[LogicalProcessorCount](#logical-processor-count)
[StartTimestamp](#start-timestamp)
[StopTimestamp](#stop-timestamp)
[TickFrequency](#tick-frequency)

## <a name="duration"></a><a name="duration"></a> Duration

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>返回值

活动的持续时间（以纳秒为单位）。

## <a name="logicalprocessorcount"></a><a name="logical-processor-count"></a> LogicalProcessorCount

```cpp
const unsigned long& LogicalProcessorCount() const;
```

### <a name="return-value"></a>返回值

收集跟踪的计算机上的逻辑处理器数。

## <a name="starttimestamp"></a><a name="start-timestamp"></a> StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>返回值

在启动跟踪时捕获的滴答值。

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a> StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>返回值

在停止跟踪时捕获的滴答值。

## <a name="tickfrequency"></a><a name="tick-frequency"></a> TickFrequency

```cpp
const long long& TickFrequency() const;
```

### <a name="return-value"></a>返回值

在计算持续时间（以“滴答”为计量单位）时使用的每秒滴答数。

## <a name="traceinfo"></a><a name="trace-info"></a> TraceInfo

```cpp
TraceInfo(const TRACE_INFO_DATA& data);
```

### <a name="parameters"></a>参数

data\
包含有关跟踪的信息的数据。

::: moniker-end
