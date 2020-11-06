---
title: OnTraceInfoFunc typedef
description: C++ Build Insights SDK OnTraceInfoFunc typedef 引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OnTraceInfoFunc
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4aaa865fd0f907a67179e7ee967f23a9827b0026
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922462"
---
# <a name="ontraceinfofunc-typedef"></a>OnTraceInfoFunc typedef

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`OnTraceInfoFunc` typedef 是在 [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 和 [RELOG_CALLBACKS](relog-callbacks-struct.md) 结构中使用的函数签名之一。

## <a name="syntax"></a>语法

```cpp
typedef enum CALLBACK_CODE (BUILD_INSIGHTS_API *OnTraceInfoFunc)(
    const TRACE_INFO_DATA*          traceInfo,
    void*                           callbackContext);
```

### <a name="parameters"></a>参数

traceInfo\
包含有关当前正在分析或重新记录的跟踪的信息的 [TRACE_INFO_DATA](../c-event-data-types/trace-info-data-struct.md) 对象。

callbackContext\
在 [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) 或 [RELOG_DESCRIPTOR](relog-descriptor-struct.md) 中为此回调设置的上下文值。

### <a name="return-value"></a>返回值

控制接下来应执行的操作的 [CALLBACK_CODE](callback-code-enum.md) 值。

::: moniker-end
