---
description: 了解详细信息： &lt; chrono &gt; 函数
title: '&lt;chrono&gt; 函数'
ms.date: 11/04/2016
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
ms.openlocfilehash: 161edeccace243c10a6382d931f5f9387f35790d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234197"
---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt; 函数

## <a name="duration_cast"></a><a name="duration_cast"></a> duration_cast

将 `duration` 对象转换为指定类型。

```cpp
template <class To, class Rep, class Period>
constexpr To duration_cast(const duration<Rep, Period>& Dur);

template <class ToDuration, class Rep, class Period>
constexpr ToDuration floor(const duration<Rep, Period>& d);
template <class ToDuration, class Rep, class Period>
constexpr ToDuration ceil(const duration<Rep, Period>& d);
template <class ToDuration, class Rep, class Period>
constexpr ToDuration round(const duration<Rep, Period>& d);
```

### <a name="return-value"></a>返回值

一个表示时间间隔 `Dur` 的 `To` 类型的 `duration` 对象，需进行截断才能适应目标类型大小。

### <a name="remarks"></a>备注

如果 `To` 为 `duration` 的实例化，则此函数不参与重载决策。

## <a name="time_point_cast"></a><a name="time_point_cast"></a> time_point_cast

将 [time_point](../standard-library/time-point-class.md) 对象转换为指定类型。

```cpp
template <class To, class Clock, class Duration>
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);

template <class ToDuration, class Clock, class Duration>
constexpr time_point<Clock, ToDuration>
floor(const time_point<Clock, Duration>& tp);
template <class ToDuration, class Clock, class Duration>
constexpr time_point<Clock, ToDuration>
ceil(const time_point<Clock, Duration>& tp);
template <class ToDuration, class Clock, class Duration>
constexpr time_point<Clock, ToDuration>
round(const time_point<Clock, Duration>& tp);
```

### <a name="return-value"></a>返回值

持续时间为 `To` 类型的 `time_point` 对象。

### <a name="remarks"></a>备注

除非 `To` 为 [duration](../standard-library/duration-class.md) 的实例化，否则函数不参与重载决策。
