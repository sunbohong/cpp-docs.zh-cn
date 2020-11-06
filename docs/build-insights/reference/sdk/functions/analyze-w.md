---
title: AnalyzeW
description: C++ Build Insights SDK AnalyzeW 函数引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalyzeW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a75668e0fc9d356315f5f0b3156a909187415521
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922860"
---
# <a name="analyzew"></a>AnalyzeW

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`AnalyzeW` 函数用于分析从输入 Windows 事件跟踪 (ETW) 跟踪读取的 MSVC 事件。

## <a name="syntax"></a>语法

```cpp
enum RESULT_CODE AnalyzeW(
    const wchar_t*             inputLogFile,
    const ANALYSIS_DESCRIPTOR* analysisDescriptor);
```

### <a name="parameters"></a>参数

inputLogFile\
要从中读取事件的输入 ETW 跟踪。

analysisDescriptor\
指向 [ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) 对象的指针。 使用此对象配置分析。

### <a name="return-value"></a>返回值

[RESULT_CODE](../other-types/result-code-enum.md) 枚举中的结果代码。

::: moniker-end
