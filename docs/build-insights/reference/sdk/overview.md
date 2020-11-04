---
title: C++ 生成见解 SDK
description: 概述了 Visual Studio C++ Build Insights SDK。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyzing
- Relogging
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a6ecff81a9f3d2b22107a8fa7fc26fad85d4f579
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919509"
---
# <a name="c-build-insights-sdk"></a>C++ 生成见解 SDK

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

C++ Build Insights SDK 是一个 API 集合，可便于在 C++ Build Insights 平台基础之上创建个性化工具。 本页提供了有助于你入门的简要概述。

## <a name="obtaining-the-sdk"></a>获取 SDK

可以将 C++ Build Insights SDK 下载为 NuGet 包，具体步骤如下：

1. 在 Visual Studio 2017 及更高版本中，新建 C++ 项目。
1. 在“解决方案资源管理器”窗格中，右键单击你的项目。
1. 选择关联菜单中的“管理 NuGet 包”。
1. 选择右上角的“nuget.org”包源。
1. 搜索最新版 Microsoft.Cpp.BuildInsights 包。
1. 选择“安装”。
1. 接受许可证。

继续阅读有关此 SDK 的一般概念的信息。 你还可以访问官方的 [C++ Build Insights 示例 GitHub 存储库](https://github.com/microsoft/cpp-build-insights-samples)，以查看使用此 SDK 的实际 C++ 应用程序示例。

## <a name="collecting-a-trace"></a>收集跟踪

若要使用 C++ Build Insights SDK 分析来自 MSVC 工具链的事件，需要先收集跟踪。 此 SDK 使用 Windows 事件跟踪 (ETW) 作为基础跟踪技术。 可以通过两种方式来收集跟踪：

### <a name="method-1-using-vcperf-in-visual-studio-2019-and-above"></a>方法 1：在 Visual Studio 2019 及更高版本中使用 vcperf

1. 打开适用于 VS 2019 的提升的 x64 本机工具命令提示。
1. 运行以下命令：`vcperf /start MySessionName`
1. 生成你的项目。
1. 运行以下命令：`vcperf /stopnoanalyze MySessionName outputTraceFile.etl`

   > [!IMPORTANT]
   > 使用 vcperf 停止跟踪时，请运行 `/stopnoanalyze` 命令。 不能使用 C++ Build Insights SDK 来分析由常规 `/stop` 命令停止的跟踪。

### <a name="method-2-programmatically"></a>方法 2：以编程方式

使用下面这些 C++ Build Insights SDK 跟踪收集函数来以编程方式启动和停止跟踪。 执行这些函数调用的程序必须有管理权限。 只有启动和停止跟踪函数需要管理权限。 C++ Build Insights SDK 中的其他所有函数都可以在没有管理权限的情况下执行。

### <a name="sdk-functions-related-to-trace-collection"></a>与跟踪收集相关的 SDK 函数

| 功能 | C++ API | C API |
|--|--|--|
| 启动跟踪 | [StartTracingSession](functions/start-tracing-session.md) | [StartTracingSessionA](functions/start-tracing-session-a.md)<br />[StartTracingSessionW](functions/start-tracing-session-w.md) |
| 停止跟踪 | [StopTracingSession](functions/stop-tracing-session.md) | [StopTracingSessionA](functions/stop-tracing-session-a.md)<br />[StopTracingSessionW](functions/stop-tracing-session-w.md) |
| 停止跟踪并<br />立即分析结果 | [StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session.md) | [StopAndAnalyzeTracingSessionA](functions/stop-and-analyze-tracing-session-a.md)<br />[StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session-w.md) |
| 停止跟踪并<br />立即重新记录结果 | [StopAndRelogTracingSession](functions/stop-and-relog-tracing-session.md) | [StopAndRelogTracingSessionA](functions/stop-and-relog-tracing-session-a.md)<br />[StopAndRelogTracingSessionW](functions/stop-and-relog-tracing-session-w.md) |

接下来的各部分介绍了如何配置分析或重新记录会话。 这是合并的功能函数（如 [StopAndAnalyzeTracingSession](functions/stop-and-analyze-tracing-session.md)）所必需的。

## <a name="consuming-a-trace"></a>使用跟踪

有了 ETW 跟踪之后，使用 C++ Build Insights SDK 来解包它。 此 SDK 以一种可便于快速开发工具的格式提供事件。 不建议在不使用此 SDK 的情况下使用原始 ETW 跟踪。 MSVC 使用的事件格式是没有文档记录的，经过优化可以扩展为大型生成，并且很难理解。 此外，C++ Build Insights SDK API 是稳定的，而原始 ETW 跟踪格式可能会在不另行通知的情况下发生变更。

### <a name="sdk-types-and-functions-related-to-trace-consumption"></a>与跟踪使用相关的 SDK 类型和函数

| 功能 | C++ API | C API | 说明 |
|--|--|--|--|
| 创建事件回叫 | [IAnalyzer](other-types/ianalyzer-class.md)<br />[IRelogger](other-types/irelogger-class.md) | [ANALYSIS_CALLBACKS](other-types/analysis-callbacks-struct.md)<br />[RELOG_CALLBACKS](other-types/relog-callbacks-struct.md) | C++ Build Insights SDK 通过回叫函数提供事件。 在 C++ 中，通过创建继承自 IAnalyzer 或 IRelogger 接口的 analyzer 或 relogger 类来实现回叫函数。 在 C 中，在全局函数中实现回叫，并在 ANALYSIS_CALLBACKS 或 RELOG_CALLBACKS 结构中提供指向它们的指针。 |
| 生成组 | [MakeStaticAnalyzerGroup](functions/make-static-analyzer-group.md)<br />[MakeStaticReloggerGroup](functions/make-static-relogger-group.md)<br />[MakeDynamicAnalyzerGroup](functions/make-dynamic-analyzer-group.md)<br />[MakeDynamicReloggerGroup](functions/make-dynamic-relogger-group.md) |  | C++ API 提供了帮助程序函数和类型，以将多个 analyzer 和 relogger 对象组合在一起。 分组是一种将复杂分析划分为更简单步骤的简洁方法。 [vcperf](https://github.com/microsoft/vcperf) 就是按照这种方法进行组织的。 |
| 分析或重新记录 | [分析](functions/analyze.md)<br />[Relog](functions/relog.md) | [AnalyzeA](functions/analyze-a.md)<br />[AnalyzeW](functions/analyze-w.md)<br />[RelogA](functions/relog-a.md)<br />[RelogW](functions/relog-w.md) |  |

### <a name="analyzing-and-relogging"></a>分析和重新记录

跟踪使用是通过分析会话或重新记录会话来完成的。

使用常规分析适用于大多数情况。 使用这种方法，可以灵活地选择输出格式：`printf` 文本、xml、JSON、数据库、REST 调用等。

重新记录用于需要生成 ETW 输出文件的特殊用途分析。 使用重新记录，可以将 C++ Build Insights 事件转换为采用你自己的 ETW 事件格式。 重新记录的一种合适用法是，将 C++ Build Insights 数据挂钩到现有的 ETW 工具和基础结构。 例如，[vcperf](https://github.com/microsoft/vcperf) 使用了重新记录接口。 这是因为它必须生成作为 ETW 工具的 Windows Performance Analyzer 可以理解的数据。 如果你计划使用重新记录接口，则需要预先了解 ETW 的工作原理。

### <a name="creating-analyzer-groups"></a>创建 analyzer 组

请务必了解如何创建组。 下面的示例展示了如何创建 analyzer 组，为它收到的每个活动启动事件 打印“Hello, world!”。

```cpp
using namespace Microsoft::Cpp::BuildInsights;

class Hello : public IAnalyzer
{
public:
    AnalysisControl OnStartActivity(
        const EventStack& eventStack) override
    {
        std::cout << "Hello, " << std::endl;
        return AnalysisControl::CONTINUE;
    }
};

class World : public IAnalyzer
{
public:
    AnalysisControl OnStartActivity(
        const EventStack& eventStack) override
    {
        std::cout << "world!" << std::endl;
        return AnalysisControl::CONTINUE;
    }
};

int main()
{
    Hello hello;
    World world;

    // Let's make Hello the first analyzer in the group
    // so that it receives events and prints "Hello, "
    // first.
    auto group = MakeStaticAnalyzerGroup(&hello, &world);

    unsigned numberOfAnalysisPasses = 1;

    // Calling this function initiates the analysis and
    // forwards all events from "inputTrace.etl" to my analyzer
    // group.
    Analyze("inputTrace.etl", numberOfAnalysisPasses, group);

    return 0;
}
```

## <a name="using-events"></a>使用事件

### <a name="sdk-types-and-functions-related-to-events"></a>与事件相关的 SDK 类型和函数

| 功能 | C++ API | C API | 说明 |
|--|--|--|--|
| 匹配和筛选事件 | [MatchEventStackInMemberFunction](functions/match-event-stack-in-member-function.md)<br />[MatchEventStack](functions/match-event-stack.md)<br />[MatchEventInMemberFunction](functions/match-event-in-member-function.md)<br />[MatchEvent](functions/match-event.md) |  | 此 C++ API 提供了一些函数，可便于你从跟踪中轻松地提取你关注的事件。 使用此 C API 时，必须手动完成这种筛选。 |
| 事件数据类型 | [活动](cpp-event-data-types/activity.md)<br />[BackEndPass](cpp-event-data-types/back-end-pass.md)<br />[BottomUp](cpp-event-data-types/bottom-up.md)<br />[C1DLL](cpp-event-data-types/c1-dll.md)<br />[C2DLL](cpp-event-data-types/c2-dll.md)<br />[CodeGeneration](cpp-event-data-types/code-generation.md)<br />[CommandLine](cpp-event-data-types/command-line.md)<br />[Compiler](cpp-event-data-types/compiler.md)<br />[CompilerPass](cpp-event-data-types/compiler-pass.md)<br />[EnvironmentVariable](cpp-event-data-types/environment-variable.md)<br />[事件](cpp-event-data-types/event.md)<br />[EventGroup](cpp-event-data-types/event-group.md)<br />[EventStack](cpp-event-data-types/event-stack.md)<br />[ExecutableImageOutput](cpp-event-data-types/executable-image-output.md)<br />[ExpOutput](cpp-event-data-types/exp-output.md)<br />[FileInput](cpp-event-data-types/file-input.md)<br />[FileOutput](cpp-event-data-types/file-output.md)<br />[ForceInlinee](cpp-event-data-types/force-inlinee.md)<br />[FrontEndFile](cpp-event-data-types/front-end-file.md)<br />[FrontEndFileGroup](cpp-event-data-types/front-end-file-group.md)<br />[FrontEndPass](cpp-event-data-types/front-end-pass.md)<br />[Function](cpp-event-data-types/function.md)<br />[ImpLibOutput](cpp-event-data-types/imp-lib-output.md)<br />[调用](cpp-event-data-types/invocation.md)<br />[InvocationGroup](cpp-event-data-types/invocation-group.md)<br />[LibOutput](cpp-event-data-types/lib-output.md)<br />[链接器](cpp-event-data-types/linker.md)<br />[LinkerGroup](cpp-event-data-types/linker-group.md)<br />[LinkerPass](cpp-event-data-types/linker-pass.md)<br />[LTCG](cpp-event-data-types/ltcg.md)<br />[ObjOutput](cpp-event-data-types/obj-output.md)<br />[OptICF](cpp-event-data-types/opt-icf.md)<br />[OptLBR](cpp-event-data-types/opt-lbr.md)<br />[OptRef](cpp-event-data-types/opt-ref.md)<br />[Pass1](cpp-event-data-types/pass1.md)<br />[Pass2](cpp-event-data-types/pass2.md)<br />[PreLTCGOptRef](cpp-event-data-types/pre-ltcg-opt-ref.md)<br />[SimpleEvent](cpp-event-data-types/simple-event.md)<br />[SymbolName](cpp-event-data-types/symbol-name.md)<br />[TemplateInstantiation](cpp-event-data-types/template-instantiation.md)<br />[TemplateInstantiationGroup](cpp-event-data-types/template-instantiation-group.md)<br />[线程](cpp-event-data-types/thread.md)<br />[TopDown](cpp-event-data-types/top-down.md)<br />[TraceInfo](cpp-event-data-types/trace-info.md)<br />[WholeProgramAnalysis](cpp-event-data-types/whole-program-analysis.md) | [CL_PASS_DATA](c-event-data-types/cl-pass-data-struct.md)<br />[EVENT_COLLECTION_DATA](c-event-data-types/event-collection-data-struct.md)<br />[EVENT_DATA](c-event-data-types/event-data-struct.md)<br />[EVENT_ID](c-event-data-types/event-id-enum.md)<br />[FILE_DATA](c-event-data-types/file-data-struct.md)<br />[FILE_TYPE_CODE](c-event-data-types/file-type-code-enum.md)<br />[FRONT_END_FILE_DATA](c-event-data-types/front-end-file-data-struct.md)<br />[FUNCTION_DATA](c-event-data-types/function-data-struct.md)<br />[FUNCTION_FORCE_INLINEE_DATA](c-event-data-types/function-force-inlinee-data-struct.md)<br />[INVOCATION_DATA](c-event-data-types/invocation-data-struct.md)<br />[INVOCATION_VERSION_DATA](c-event-data-types/invocation-version-data-struct.md)<br />[MSVC_TOOL_CODE](c-event-data-types/msvc-tool-code-enum.md)<br />[NAME_VALUE_PAIR_DATA](c-event-data-types/name-value-pair-data-struct.md)<br />[SYMBOL_NAME_DATA](c-event-data-types/symbol-name-data-struct.md)<br />[TEMPLATE_INSTANTIATION_DATA](c-event-data-types/template-instantiation-data-struct.md)<br />[TEMPLATE_INSTANTIATION_KIND_CODE](c-event-data-types/template-instantiation-kind-code-enum.md)<br />[TRACE_INFO_DATA](c-event-data-types/trace-info-data-struct.md)<br />[TRANSLATION_UNIT_PASS_CODE](c-event-data-types/translation-unit-pass-code-enum.md) |  |

### <a name="activities-and-simple-events"></a>活动和简单事件

事件分为“活动”和“简单事件”这两类。 活动是指正在进行的进程，有开始时间，也有结束时间。 简单事件是准时发生的，没有持续时间。 当使用 C++ Build Insights SDK 分析 MSVC 跟踪时，你会在活动开始和停止时收到单独的事件。 当一个简单事件发生时，你将只收到一个事件。

### <a name="parent-child-relationships"></a>父子关系

活动和简单事件通过父子关系相互关联。 活动或简单事件的父级是包含它们的活动。 例如，在编译源文件时，编译器必须先分析文件，再生成代码。 分析文件和代码生成这两个活动都是编译器活动的子级。

由于简单事件没有持续时间，因此其内部不会发生其他任何事件。 所以，简单事件从来没有任何子级。

每个活动和简单事件的父子关系在[事件表](event-table.md)中指明。 使用 C++ Build Insights 事件时，请务必了解这些关系。 你常常不得不依赖他们来理解事件的完整上下文。

### <a name="properties"></a>属性

所有事件都具有以下属性：

| Property | 描述 |
|--|--|
| 类型标识符 | 唯一标识事件类型的编号。 |
| 实例标识符 | 在跟踪内唯一标识事件的编号。 如果在跟踪中发生了相同类型的两个事件，那么两个事件都将获得唯一的实例标识符。 |
| 开始时间 | 活动启动的时间或简单事件发生的时间。 |
| 进程标识符 | 标识事件发生进程的编号。 |
| 线程标识符 | 标识事件发生线程的编号。 |
| 处理器索引 | 指明事件由哪个逻辑处理器发出的从零开始编制的索引。 |
| 事件名称 | 描述事件类型的字符串。 |

除简单事件之外的所有活动也都具有以下属性：

| Property | 描述 |
|--|--|
| 停止时间 | 活动停止时间。 |
| 独占持续时间 | 花费在某项活动上的时间，不包括花费在其子活动上的时间。 |
| CPU 时间 | CPU 在附加到活动的线程中执行代码所花费的时间。 它不包括附加到活动的线程的休眠时间。 |
| 独占 CPU 时间 | 与 CPU 时间相同，但不包括子活动所花费的 CPU 时间。 |
| 时钟时间责任 | 活动对总时钟时间的贡献。 时钟时间责任将活动之间的并行度考虑在内。 例如，假设两个不相关的活动并行运行。 两个活动的持续时间都是 10 秒，且开始时间和停止时间完全相同。 在这种情况下，Build Insights 分配的时钟时间责任都是 5 秒。 相反，如果这些活动一个接一个地运行且没有重叠，则为它们分配的时钟时间责任都是 10 秒。 |
| 独占时钟时间责任 | 与时钟时间责任相同，但不包括子活动的时钟时间责任。 |

有些事件除了上面提到的属性外，还有它们自己的属性。 在这种情况下，这些附加属性列在[事件表](event-table.md)中。

### <a name="consuming-events-provided-by-the-c-build-insights-sdk"></a>使用 C++ Build Insights SDK 提供的事件

#### <a name="the-event-stack"></a>事件堆栈

每当 C++ Build Insights SDK 提供事件时，它都以堆栈的形式出现。 堆栈中的最后一个条目是当前事件，在它之前的条目是它的父层次结构。 例如，[LTCG](event-table.md#ltcg) 启动和停止事件发生在链接器的第 1 阶段。 在此示例中，你将收到的堆栈包含：\[[LINKER](event-table.md#linker), [PASS1](event-table.md#pass1), LTCG\]。 父层次结构很方便，因为可以将事件追溯到它的根。 如果上面提到的 LTCG 活动比较慢，则可以立即了解涉及到哪个链接器调用。

#### <a name="matching-events-and-event-stacks"></a>匹配事件和事件堆栈

C++ Build Insights SDK 为你提供了跟踪中的所有事件，但大多数情况下你只关注其中一部分。 在某些情况下，你可能只关注事件堆栈的一部分。 SDK 提供了一些工具，可帮助你快速提取所需的事件或事件堆栈，并拒绝不需要的事件或事件堆栈。 这是通过下面这些匹配函数来完成的：

| 函数 | 描述 |
|--|--|
| [MatchEvent](functions/match-event.md) | 如果事件与指定的类型之一匹配，则予以保留。 将匹配的事件转发给 lambda 或其他可调用类型。 此函数不考虑事件的父层次结构。 |
| [MatchEventInMemberFunction](functions/match-event-in-member-function.md) | 如果事件与成员函数的参数中指定的类型匹配，则予以保留。 将匹配的事件转发给成员函数。 此函数不考虑事件的父层次结构。 |
| [MatchEventStack](functions/match-event-stack.md) | 如果事件及其父层次结构都与指定的类型匹配，则予以保留。 将事件和匹配的父层次结构事件转发给 lambda 或其他可调用类型。 |
| [MatchEventStackInMemberFunction](functions/match-event-stack-in-member-function.md) | 如果事件及其父层次结构都与成员函数的参数列表中指定的类型匹配，则予以保留。 将事件和匹配的父层次结构事件转发给成员函数。 |

事件堆栈匹配函数（如 `MatchEventStack`）在描述要匹配的父层次结构时允许存在间隙。 例如，你可能会表示自己关注 \[[LINKER](event-table.md#linker), [LTCG](event-table.md#ltcg)\] 堆栈。 它还会匹配 \[LINKER, [PASS1](event-table.md#pass1), LTCG\] 堆栈。 指定的最后一个类型必须是要匹配的事件类型，并且不属于父层次结构。

#### <a name="capture-classes"></a>Capture 类

使用 `Match*` 函数需要指定要匹配的类型。 这些类型是从捕获类列表中选择的。 捕获类分为几个类别，如下所述。

| 类别 | 描述 |
|--|--|
| Exact | 此类捕获类用于匹配特定的事件类型，而不是其他类型。 例如，[Compiler](cpp-event-data-types/compiler.md) 类匹配 [COMPILER](event-table.md#compiler) 事件。 |
| 通配符 | 此类捕获类可用于匹配它们所支持的事件列表中的任何事件。 例如，[Activity](cpp-event-data-types/activity.md) 通配符匹配任何活动事件。 再例如，[CompilerPass](cpp-event-data-types/compiler-pass.md) 通配符可以匹配 [FRONT_END_PASS](event-table.md#front-end-pass) 或 [BACK_END_PASS](event-table.md#back-end-pass) 事件。 |
| 组 | 组捕获类的名称以 Group 结尾。 它们用于匹配连续多个类型相同的事件，同时忽略间隙。 它们只有在匹配递归事件时才有意义，因为你不知道事件堆栈中有多少事件。 例如，每当编译器分析文件时，[FRONT_END_FILE](event-table.md#front-end-file) 活动都会发生。 此活动是递归的，因为编译器在分析文件时可能会发现 include 指令。 [FrontEndFile](cpp-event-data-types/front-end-file.md) 类只匹配堆栈中的一个 FRONT_END_FILE 事件。 使用 [FrontEndFileGroup](cpp-event-data-types/front-end-file-group.md) 类可以匹配整个 include 层次结构。 |
| 通配符组 | 通配符组将通配符和组的属性合并在一起。 此类别的唯一类是 [InvocationGroup](cpp-event-data-types/invocation-group.md)，它匹配并捕获一个事件堆栈中的所有 [LINKER](event-table.md#linker) 和 [COMPILER](event-table.md#compiler) 事件。 |

请参阅[事件表](event-table.md)，了解可以使用哪些捕获类来匹配每个事件。

#### <a name="after-matching-using-captured-events"></a>匹配后：使用捕获的事件

在成功完成匹配后，`Match*` 函数便会构造捕获类对象，并将它们转发给指定的函数。 使用这些捕获类对象可以访问事件的属性。

#### <a name="example"></a>示例

```cpp
AnalysisControl MyAnalyzer::OnStartActivity(const EventStack& eventStack)
{
    // The event types to match are specified in the PrintIncludes function
    // signature.  
    MatchEventStackInMemberFunction(eventStack, this, &MyAnalyzer::PrintIncludes);
}

// We want to capture event stacks where:
// 1. The current event is a FrontEndFile activity.
// 2. The current FrontEndFile activity has at least one parent FrontEndFile activity
//    and possibly many.
void PrintIncludes(FrontEndFileGroup parentIncludes, FrontEndFile currentFile)
{
    // Once we reach this point, the event stack we are interested in has been matched.
    // The current FrontEndFile activity has been captured into 'currentFile', and
    // its entire inclusion hierarchy has been captured in 'parentIncludes'.

    cout << "The current file being parsed is: " << currentFile.Path() << endl;
    cout << "This file was reached through the following inclusions:" << endl;

    for (auto& f : parentIncludes)
    {
        cout << f.Path() << endl;
    }
}
```

::: moniker-end
