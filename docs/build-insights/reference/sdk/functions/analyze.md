---
title: 分析
description: C++ Build Insights SDK Analyze 函数引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Analyze
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5e593b690231adf6f04161f9c3ff6aef3217f9ef
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920315"
---
# <a name="analyze"></a>分析

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`Analyze` 函数用于分析在跟踪 C++ 生成时从 MSVC 中获取的 Windows 事件跟踪 (ETW) 跟踪。 ETW 跟踪中的事件按顺序转发到调用方提供的分析器组。 此函数支持多传递分析，允许在一行中多次将事件流转发到分析器组。

## <a name="syntax"></a>语法

```cpp
template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const char*                                   inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);

template <typename... TAnalyzerGroupMembers>
RESULT_CODE Analyze(
    const wchar_t*                                inputLogFile,
    unsigned                                      numberOfPasses,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup);
```

### <a name="parameters"></a>参数

TAnalyzerGroupMembers\
此参数始终是推导出来的。

inputLogFile\
要从中读取事件的输入 ETW 跟踪。

numberOfPasses\
要在输入跟踪上运行的分析传递数。 每个分析传递通过提供的分析器组传递一次跟踪。

analyzerGroup\
用于分析的分析器组。 调用 [MakeStaticAnalyzerGroup](make-static-analyzer-group.md) 以创建分析器组。 若要使用从 [MakeDynamicAnalyzerGroup](make-dynamic-analyzer-group.md) 中获取的动态分析器组，请先通过将其地址传递给 `MakeStaticAnalyzerGroup` 来将该组封装在静态分析器组内。

### <a name="return-value"></a>返回值

[RESULT_CODE](../other-types/result-code-enum.md) 枚举中的结果代码。

::: moniker-end
