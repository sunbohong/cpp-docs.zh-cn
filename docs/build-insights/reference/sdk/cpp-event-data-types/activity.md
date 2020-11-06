---
title: Activity 类
description: C++ Build Insights SDK Activity 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Activity
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ce7e4083411f1654064ca4628d10a767c7be1b7f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923400"
---
# <a name="activity-class"></a>Activity 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`Activity` 类与 [MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md) 和 [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 函数一起结合使用。 使用它来匹配任何活动事件。 若要查看可由 `Activity` 类匹配的所有事件，请参阅[事件表](../event-table.md)。

## <a name="syntax"></a>语法

```cpp
class Activity : public Event
{
public:
    Activity(const RawEvent& event);

    const long long& StartTimestamp() const;
    const long long& StopTimestamp() const;
    const long long& ExclusiveDurationTicks() const;
    const long long& CPUTicks() const;
    const long long& ExclusiveCPUTicks() const;
    const long long& WallClockTimeResponsibilityTicks() const;
    const long long& ExclusiveWallClockTimeResponsibilityTicks() const;

    std::chrono::nanoseconds Duration() const;
    std::chrono::nanoseconds ExclusiveDuration() const;
    std::chrono::nanoseconds CPUTime() const ;
    std::chrono::nanoseconds ExclusiveCPUTime() const;
    std::chrono::nanoseconds WallClockTimeResponsibility() const;
    std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
};
```

## <a name="remarks"></a>备注

`Activity` 类中的几个成员函数返回滴答计数。 C++ Build Insights 使用 Windows 的性能计数器作为滴答源。 滴答计数必须与滴答频率一起使用，以将其转换为时间单位（如秒）。 可以调用 [Event](event.md) 基类中提供的 `TickFrequency` 成员函数以获取滴答频率。 [EVENT_DATA](../c-event-data-types/event-data-struct.md#tick-conversion-example) 页显示了将滴答数转换为时间单位的示例。

如果你不想自行将滴答数转换为时间单位，则 `Activity` 类将提供返回时间值（以纳秒为单位）的成员函数。 使用标准 C++ `chrono` 库将它们转换为其他时间单位。

## <a name="members"></a>成员

除了从 [Event](event.md) 基类继承的成员外，`Activity` 类还包含以下成员：

### <a name="constructor"></a>构造函数

[活动](#activity)

### <a name="functions"></a>函数

[CPUTicks](#cpu-ticks)\
[CPUTime](#cpu-time)\
[Duration](#duration)\
[ExclusiveCPUTicks](#exclusive-cpu-ticks)\
[ExclusiveCPUTime](#exclusive-cpu-time)\
[ExclusiveDuration](#exclusive-duration)\
[ExclusiveDurationTicks](#exclusive-duration-ticks)\
[ExclusiveWallClockTimeResponsibility](#exclusive-wall-clock-time-responsibility)\
[ExclusiveWallClockTimeResponsibilityTicks](#exclusive-wall-clock-time-responsibility-ticks)\
[StartTimestamp](#start-timestamp)\
[StopTimestamp](#stop-timestamp)\
[WallClockTimeResponsibility](#wall-clock-time-responsibility)\
[WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks)

## <a name="activity"></a><a name="activity"></a> 活动

```cpp
Activity(const RawEvent& event);
```

### <a name="parameters"></a>参数

*event*\
任何活动事件。

## <a name="cputicks"></a><a name="cpu-ticks"></a> CPUTicks

```cpp
const long long& CPUTicks() const;
```

### <a name="return-value"></a>返回值

此活动期间发生的 CPU 滴答数。 CPU 滴答不同于常规滴答。 只有当 CPU 在活动中执行代码时，才对 CPU 滴答进行计数。 当与活动关联的线程处于睡眠状态时，不会对 CPU 滴答进行计数。

## <a name="cputime"></a><a name="cpu-time"></a> CPUTime

```cpp
std::chrono::nanoseconds CPUTime()() const;
```

### <a name="return-value"></a>返回值

CPU 在此活动内执行代码的时间。 如果子活动在单独的线程上执行，则此值可能高于活动的持续时间。 该值以纳秒为单位返回。

## <a name="duration"></a><a name="duration"></a> Duration

```cpp
std::chrono::nanoseconds Duration() const;
```

### <a name="return-value"></a>返回值

活动的持续时间（以纳秒为单位）。

## <a name="exclusivecputicks"></a><a name="exclusive-cpu-ticks"></a> ExclusiveCPUTicks

```cpp
const long long& ExclusiveCPUTicks() const;
```

### <a name="return-value"></a>返回值

与 [CPUTicks](#cpu-ticks) 相同，但不包括子活动中发生的 CPU 滴答。

## <a name="exclusivecputime"></a><a name="exclusive-cpu-time"></a> ExclusiveCPUTime

```cpp
std::chrono::nanoseconds ExclusiveCPUTime() const;
```

### <a name="return-value"></a>返回值

与 [CPUTime](#cpu-time) 相同，不同之处在于子活动的 CPU 时间不包括在内。

## <a name="exclusiveduration"></a><a name="exclusive-duration"></a> ExclusiveDuration

```cpp
std::chrono::nanoseconds ExclusiveDuration() const;
```

### <a name="return-value"></a>返回值

活动的持续时间（以纳秒为单位），不包括子活动中所用的时间。

## <a name="exclusivedurationticks"></a><a name="exclusive-duration-ticks"></a> ExclusiveDurationTicks

```cpp
const long long& ExclusiveDurationTicks() const;
```

### <a name="return-value"></a>返回值

此活动中发生的滴答数，不包括子活动中发生的滴答数。

## <a name="exclusivewallclocktimeresponsibility"></a><a name="exclusive-wall-clock-time-responsibility"></a> ExclusiveWallClockTimeResponsibility

```cpp
std::chrono::nanoseconds ExclusiveWallClockTimeResponsibility() const;
```

### <a name="return-value"></a>返回值

与 [WallClockTimeResponsibility](#wall-clock-time-responsibility) 相同，但不包括子活动的时钟时间责任。

## <a name="exclusivewallclocktimeresponsibilityticks"></a><a name="exclusive-wall-clock-time-responsibility-ticks"></a> ExclusiveWallClockTimeResponsibilityTicks

```cpp
const long long& ExclusiveWallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>返回值

与 [WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks) 相同，但不包括子活动的时钟时间责任滴答。

## <a name="starttimestamp"></a><a name="start-timestamp"></a> StartTimestamp

```cpp
const long long& StartTimestamp() const;
```

### <a name="return-value"></a>返回值

活动开始时捕获的滴答值。

## <a name="stoptimestamp"></a><a name="stop-timestamp"></a> StopTimestamp

```cpp
const long long& StopTimestamp() const;
```

### <a name="return-value"></a>返回值

活动停止时捕获的滴答值。

## <a name="wallclocktimeresponsibility"></a><a name="wall-clock-time-responsibility"></a> WallClockTimeResponsibility

```cpp
std::chrono::nanoseconds WallClockTimeResponsibility() const;
```

### <a name="return-value"></a>返回值

此活动的时钟时间责任（以纳秒为单位）。 有关时钟时间责任的含义的详细信息，请参阅 [WallClockTimeResponsibilityTicks](#wall-clock-time-responsibility-ticks)。

## <a name="wallclocktimeresponsibilityticks"></a><a name="wall-clock-time-responsibility-ticks"></a> WallClockTimeResponsibilityTicks

```cpp
const long long& WallClockTimeResponsibilityTicks() const;
```

### <a name="return-value"></a>返回值

表示这一活动对总时钟时间的贡献的滴答计数。 时钟时间责任滴答不同于常规滴答。 时钟时间责任滴答考虑了活动之间的并行度。 两个并行活动的持续时间可能为 50 个滴答，并且开始时间和停止时间相同。 在此示例中，两个活动都会分配有 25 个时钟时间责任滴答。

::: moniker-end
