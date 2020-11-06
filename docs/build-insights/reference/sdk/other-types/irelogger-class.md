---
title: IRelogger 类
description: C++ Build Insights SDK IRelogger 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IRelogger
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e504ece95529f7279650062145f3ac0914449c98
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922522"
---
# <a name="irelogger-class"></a>IRelogger 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`IRelogger` 类提供用于重新记录 Windows 事件跟踪 (ETW) 跟踪的接口。 它与 [MakeDynamicReloggerGroup](../functions/make-dynamic-relogger-group.md) 和 [MakeStaticReloggerGroup](../functions/make-static-analyzer-group.md) 函数一起使用。 使用 `IRelogger` 作为基类来创建自己的重新记录器，该重新记录器可以是重新记录器组的一部分。

## <a name="syntax"></a>语法

```cpp
class IRelogger
{
public:
    virtual AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
    virtual AnalysisControl OnBeginRelogging();
    virtual AnalysisControl OnEndRelogging();
    virtual AnalysisControl OnBeginReloggingPass();
    virtual AnalysisControl OnEndReloggingPass() ;

    virtual ~IRelogger();
};
```

## <a name="remarks"></a>备注

所有未重写的函数的默认返回值都是 `AnalysisControl::CONTINUE`。 有关详细信息，请参阅 [AnalysisControl](analysis-control-enum-class.md)。

## <a name="members"></a>成员

### <a name="destructor"></a>析构函数

[~IRelogger](#irelogger-destructor)

### <a name="functions"></a>函数

[OnBeginRelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnEndReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[OnStartActivity](#on-start-activity)\
[OnStopActivity](#on-stop-activity)\
[OnTraceInfo](#on-trace-info)

## <a name="irelogger"></a><a name="irelogger-destructor"></a> ~IRelogger

销毁 IRelogger 类。

```cpp
virtual ~IRelogger();
```

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a> OnBeginRelogging

在重新记录传递开始之前将调用此函数。

```cpp
virtual AnalysisControl OnBeginRelogging();
```

### <a name="return-value"></a>返回值

描述接下来应执行的操作的 [AnalysisControl](analysis-control-enum-class.md) 代码。

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a> OnBeginReloggingPass

在重新记录传递开始时调用此函数。

```cpp
virtual AnalysisControl OnBeginReloggingPass();
```

### <a name="return-value"></a>返回值

描述接下来应执行的操作的 [AnalysisControl](analysis-control-enum-class.md) 代码。

## <a name="onendrelogging"></a><a name="on-end-relogging"></a> OnEndRelogging

在重新记录传递结束后调用此函数。

```cpp
virtual AnalysisControl OnEndRelogging();
```

### <a name="return-value"></a>返回值

描述接下来应执行的操作的 [AnalysisControl](analysis-control-enum-class.md) 代码。

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a> OnEndReloggingPass

在重新记录传递结束时调用此函数。

```cpp
virtual AnalysisControl OnEndReloggingPass();
```

### <a name="return-value"></a>返回值

描述接下来应执行的操作的 [AnalysisControl](analysis-control-enum-class.md) 代码。

## <a name="onsimpleevent"></a><a name="on-simple-event"></a> OnSimpleEvent

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

处理简单事件时调用此函数。

### <a name="parameters"></a>参数

eventStack\
此简单事件的事件堆栈。 有关事件堆栈的详细信息，请参阅[事件](../event-table.md)。

### <a name="return-value"></a>返回值

描述接下来应执行的操作的 [AnalysisControl](analysis-control-enum-class.md) 代码。

## <a name="onstartactivity"></a><a name="on-start-activity"></a> OnStartActivity

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

处理活动开始事件时将调用此函数。

### <a name="parameters"></a>参数

eventStack\
此活动开始事件的事件堆栈。 有关事件堆栈的详细信息，请参阅[事件](../event-table.md)。

### <a name="return-value"></a>返回值

描述接下来应执行的操作的 [AnalysisControl](analysis-control-enum-class.md) 代码。

## <a name="onstopactivity"></a><a name="on-stop-activity"></a> OnStopActivity

处理活动停止事件时将调用此函数。

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="parameters"></a>参数

eventStack\
此活动停止事件的事件堆栈。 有关事件堆栈的详细信息，请参阅[事件](../event-table.md)。

### <a name="return-value"></a>返回值

描述接下来应执行的操作的 [AnalysisControl](analysis-control-enum-class.md) 代码。

## <a name="ontraceinfo"></a><a name="on-trace-info"></a> OnTraceInfo

```cpp
virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
```

每次分析或重新记录传递时将调用此函数一次。

### <a name="parameters"></a>参数

traceInfo\
一个 [TraceInfo](../cpp-event-data-types/trace-info.md) 对象，该对象包含有关所使用的跟踪的有用属性。

### <a name="return-value"></a>返回值

描述接下来应执行的操作的 [AnalysisControl](analysis-control-enum-class.md) 代码。

::: moniker-end
