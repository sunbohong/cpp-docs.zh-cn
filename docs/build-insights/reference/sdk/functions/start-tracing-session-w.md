---
title: StartTracingSessionW
description: C++ Build Insights SDK StartTracingSessionW 函数引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StartTracingSessionW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d89bd6d040f9786539c9be08b9da0813d3bb2c82
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922735"
---
# <a name="starttracingsessionw"></a>StartTracingSessionW

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`StartTracingSessionW` 函数用于启动跟踪会话。 调用此函数的可执行文件必须具有管理员权限。

## <a name="syntax"></a>语法

```cpp
enum RESULT_CODE StartTracingSessionW(
    const wchar_t*                 sessionName,
    const TRACING_SESSION_OPTIONS* options);
```

### <a name="parameters"></a>参数

sessionName\
要启动的跟踪会话的名称。 调用 [StopTracingSessionW](stop-tracing-session-w.md) 或任何其他停止跟踪函数时，请使用相同的名称。

options\
指向 [TRACING_SESSION_OPTIONS](../other-types/tracing-session-options-struct.md) 对象的指针。 使用此对象可选择跟踪会话应收集的事件。

### <a name="return-value"></a>返回值

[RESULT_CODE](../other-types/result-code-enum.md) 枚举中的结果代码。

::: moniker-end
