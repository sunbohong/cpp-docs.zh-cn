---
title: IAnalyzer 类
description: C++ Build Insights SDK IAnalyzer 类引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IAnalyzer
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2514dd305a186d1153e9f9d1711bb774ea70cdf9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919808"
---
# <a name="ianalyzer-class"></a>IAnalyzer 类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`IAnalyzer` 类提供用于分析 Windows 事件跟踪 (ETW) 跟踪的接口。 它与 [MakeDynamicAnalyzerGroup](../functions/make-dynamic-analyzer-group.md)、[MakeDynamicReloggerGroup](../functions/make-dynamic-relogger-group.md)、[MakeStaticAnalyzerGroup](../functions/make-dynamic-analyzer-group.md) 和 [MakeStaticReloggerGroup](../functions/make-static-analyzer-group.md) 函数一起使用。 使用 `IAnalyzer` 作为基类来创建自己的分析器，该分析器可以是分析器或重新记录器组的一部分。

## <a name="syntax"></a>语法

```cpp
class IAnalyzer : public IRelogger
{
public:
    virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
    virtual AnalysisControl OnStopActivity(const EventStack& eventStack)
    virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
    virtual AnalysisControl OnBeginAnalysis();
    virtual AnalysisControl OnEndAnalysis();
    virtual AnalysisControl OnBeginAnalysisPass();
    virtual AnalysisControl OnEndAnalysisPass();

    AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnBeginRelogging() final;
    AnalysisControl OnEndRelogging() final;
    AnalysisControl OnBeginReloggingPass() final;
    AnalysisControl OnEndReloggingPass() final;

    virtual ~IAnalyzer();
};
```

## <a name="remarks"></a>备注

派生自 `IAnalyzer` 的类可用作分析器和重新记录器。 当用作重新记录器时，特定于重新记录器的函数会重定向到其分析器等效项。 反之则不然：派生自 `IRelogger` 的类不能用作分析器。 使用重新记录器组中的分析器是一种常见模式。 当放置在重新记录器组的前面位置时，分析器可以预先计算信息并使其可用于后面位置的重新记录器。

所有未重写的函数的默认返回值都是 `AnalysisControl::CONTINUE`。 有关详细信息，请参阅 [AnalysisControl](analysis-control-enum-class.md)。

## <a name="members"></a>成员

除了 `IRelogger` 接口中的 [OnTraceInfo](irelogger-class.md#on-trace-info) 成员以外，`IAnalyzer` 类包含以下成员：

### <a name="destructor"></a>析构函数

[~IAnalyzer](#ianalyzer-destructor)

### <a name="functions"></a>函数

[OnBeginAnalysis](#on-begin-analysis)\
[OnBeginAnalysisPass](#on-begin-analysis-pass)\
[OnBeginRelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnEndAnalysis](#on-end-analysis)\
[OnEndAnalysisPass](#on-end-analysis-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnEndReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[OnStartActivity](#on-start-activity)\
[OnStopActivity](#on-stop-activity)

## <a name="ianalyzer"></a><a name="ianalyzer-destructor"></a> ~IAnalyzer

销毁 IAnalyzer 类。

```cpp
virtual ~IAnalyzer();
```

## <a name="onbeginanalysis"></a><a name="on-begin-analysis"></a> OnBeginAnalysis

对于属于分析器组的分析器，将在第一个分析传递开始之前调用此函数。 对于属于重新记录器组的分析器，将在重新记录传递开始之前调用此函数。 对于属于同一重新记录会话的分析器和重新记录器组的分析器，将在第一个分析传递开始之前调用此函数两次。

```cpp
virtual AnalysisControl OnBeginAnalysis();
```

### <a name="return-value"></a>返回值

描述接下来应执行的操作的 [AnalysisControl](analysis-control-enum-class.md) 代码。

## <a name="onbeginanalysispass"></a><a name="on-begin-analysis-pass"></a> OnBeginAnalysisPass

对于属于分析器组的分析器，将在每次分析传递开始时调用此函数。 对于属于重新记录器组的分析器，将在每个重新记录传递开始时调用此函数。 对于属于同一重新记录会话的分析器和重新记录器组的分析器，将在每个分析传递开始时以及重新记录传递开始时调用此函数。

```cpp
virtual AnalysisControl OnBeginAnalysisPass();
```

### <a name="return-value"></a>返回值

描述接下来应执行的操作的 [AnalysisControl](analysis-control-enum-class.md) 代码。

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a> OnBeginRelogging

```cpp
AnalysisControl OnBeginRelogging() final;
```

无法重写此函数。 当分析器是重新记录器组的一部分时，C++ Build Insights SDK 会调用此函数。 此函数会将调用重定向到 [OnBeginAnalysis](#on-begin-analysis)。

### <a name="return-value"></a>返回值

[OnBeginAnalysis](#on-begin-analysis) 调用的结果。

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a> OnBeginReloggingPass

无法重写此函数。 当分析器是重新记录器组的一部分时，C++ Build Insights SDK 会调用此函数。 此函数会将调用重定向到 [OnBeginAnalysisPass](#on-begin-analysis-pass)。

```cpp
AnalysisControl OnBeginReloggingPass() final;
```

### <a name="return-value"></a>返回值

[OnBeginAnalysisPass](#on-begin-analysis-pass) 调用的结果。

## <a name="onendanalysis"></a><a name="on-end-analysis"></a> OnEndAnalysis

对于属于分析器组的分析器，将在最后一个分析传递结束之后调用此函数。 对于属于重新记录器组的分析器，将在重新记录传递结束之后调用此函数。 对于属于同一重新记录会话的分析器和重新记录器组的分析器，将调用此函数两次：

1. 在所有分析传递结束之后、在重新记录传递开始之前，以及
1. 在重新记录传递结束之后。

```cpp
virtual AnalysisControl OnEndAnalysis();
```

### <a name="return-value"></a>返回值

描述接下来应执行的操作的 [AnalysisControl](analysis-control-enum-class.md) 代码。

## <a name="onendanalysispass"></a><a name="on-end-analysis-pass"></a> OnEndAnalysisPass

对于属于分析器组的分析器，将在每个分析传递结束时调用此函数。 对于属于重新记录器组的分析器，将在每个重新记录传递结束时调用此函数。 对于属于同一重新记录会话的分析器和重新记录器组的分析器，将在每个分析传递结束时以及在重新记录传递结束时调用此函数。

```cpp
virtual AnalysisControl OnEndAnalysisPass();
```

### <a name="return-value"></a>返回值

描述接下来应执行的操作的 [AnalysisControl](analysis-control-enum-class.md) 代码。

## <a name="onendrelogging"></a><a name="on-end-relogging"></a> OnEndRelogging

无法重写此函数。 当分析器是重新记录器组的一部分时，C++ Build Insights SDK 会调用此函数。 此函数会将调用重定向到 [OnEndAnalysis](#on-end-analysis)。

```cpp
AnalysisControl OnEndRelogging() final;
```

### <a name="return-value"></a>返回值

[OnEndAnalysis](#on-end-analysis) 调用的结果。

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a> OnEndReloggingPass

无法重写此函数。 当分析器是重新记录器组的一部分时，C++ Build Insights SDK 会调用此函数。 此函数会将调用重定向到 [OnEndAnalysisPass](#on-end-analysis-pass)。

```cpp
AnalysisControl OnEndReloggingPass() final;
```

### <a name="return-value"></a>返回值

[OnEndAnalysisPass](#on-end-analysis-pass) 调用的结果。

## <a name="onsimpleevent"></a><a name="on-simple-event"></a> OnSimpleEvent

处理简单事件时调用此函数。 无法重写此函数的第二个版本。 当分析器是重新记录器组的一部分时，C++ Build Insights SDK 会调用此函数。 对版本 2 的所有调用都将重定向到版本 1。

### <a name="version-1"></a>版本 1

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

### <a name="version-2"></a>版本 2

```cpp
AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>参数

eventStack\
此简单事件的事件堆栈。 有关事件堆栈的详细信息，请参阅[事件](../event-table.md)。

relogSession\
未使用此参数。

### <a name="return-value"></a>返回值

描述接下来应执行的操作的 [AnalysisControl](analysis-control-enum-class.md) 代码。

## <a name="onstartactivity"></a><a name="on-start-activity"></a> OnStartActivity

处理活动开始事件时将调用此函数。 无法重写此函数的第二个版本。 当分析器是重新记录器组的一部分时，C++ Build Insights SDK 会调用此函数。 对版本 2 的所有调用都将重定向到版本 1。

### <a name="version-1"></a>版本 1

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

### <a name="version-2"></a>版本 2

```cpp
AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>参数

eventStack\
此活动开始事件的事件堆栈。 有关事件堆栈的详细信息，请参阅[事件](../event-table.md)。

relogSession\
未使用此参数。

### <a name="return-value"></a>返回值

描述接下来应执行的操作的 [AnalysisControl](analysis-control-enum-class.md) 代码。

## <a name="onstopactivity"></a><a name="on-stop-activity"></a> OnStopActivity

处理活动停止事件时将调用此函数。 无法重写此函数的第二个版本。 当分析器是重新记录器组的一部分时，C++ Build Insights SDK 会调用此函数。 对版本 2 的所有调用都将重定向到版本 1。

### <a name="version-1"></a>版本 1

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="version-2"></a>版本 2

```cpp
AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>参数

eventStack\
此活动停止事件的事件堆栈。 有关事件堆栈的详细信息，请参阅[事件](../event-table.md)。

relogSession\
未使用此参数。

### <a name="return-value"></a>返回值

描述接下来应执行的操作的 [AnalysisControl](analysis-control-enum-class.md) 代码。

::: moniker-end
