---
title: Relog
description: C++ Build Insights SDK Relog 函数引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Relog
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 628f60042a10cf80c0b077d28387ed75466e925b
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922748"
---
# <a name="relog"></a>Relog

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`Relog` 函数用于从 Windows 事件跟踪 (ETW) 跟踪读取 MSVC 事件，并将这些事件写入已修改的新 ETW 跟踪。

## <a name="syntax"></a>语法

```cpp
template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE Relog(
    const char*                                   inputLogFile,
    const char*                                   outputLogFile,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);

template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE Relog(
    const wchar_t*                                inputLogFile,
    const wchar_t*                                outputLogFile,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);
```

### <a name="parameters"></a>参数

TAnalyzerGroupMembers\
此参数始终是推导出来的。

TReloggerGroupMembers\
此参数始终是推导出来的。

inputLogFile\
要从中读取事件的输入 ETW 跟踪。

outputLogFile\
要在其中写入新事件的文件。

numberOfAnalysisPasses\
要在输入跟踪上运行的分析传递数。 每个分析传递通过提供的分析器组传递一次跟踪。

systemEventsRetentionFlags\
一个位掩码，用于指定哪些系统 ETW 事件要保留在重新记录的跟踪中。 有关详细信息，请参阅 [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md)。

analyzerGroup\
用于重新记录会话的分析阶段的分析器组。 调用 [MakeStaticAnalyzerGroup](make-static-analyzer-group.md) 以创建分析器组。 若要使用从 [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md) 中获取的动态分析器组，请先通过将其地址传递给 `MakeStaticAnalyzerGroup` 来将该组封装在静态分析器组内。

reloggerGroup\
将事件重新记录到 outputLogFile 中指定的跟踪文件中的重新记录器组。 调用 [MakeStaticReloggerGroup](make-static-relogger-group.md) 以创建重新记录器组。 若要使用从 [MakeDynamicReloggerGroup](make-dynamic-relogger-group.md) 中获取的动态重新记录器组，请先通过将其地址传递给 `MakeStaticReloggerGroup` 来将该组封装在静态重新记录器组内。

### <a name="return-value"></a>返回值

[RESULT_CODE](../other-types/result-code-enum.md) 枚举中的结果代码。

### <a name="remark"></a>备注

输入跟踪通过分析器组传递 *numberOfAnalysisPasses* 次。 重新记录传递没有类似的选项。 在所有分析传递完成后，通过重新记录器组只会传递一次跟踪。

不支持重新记录来自重新记录器类中的系统事件（如 CPU 示例）。 使用 systemEventsRetentionFlags 参数确定要保留在输出跟踪中的系统事件。

::: moniker-end
