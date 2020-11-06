---
title: TRACING_SESSION_SYSTEM_EVENT_FLAGS 常量
description: C++ Build Insights SDK TRACING_SESSION_SYSTEM_EVENT_FLAGS 常量引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 346c955355ffbc6c062a34bf928f16ccd3940154
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922372"
---
# <a name="tracing_session_system_event_flags-constants"></a>TRACING_SESSION_SYSTEM_EVENT_FLAGS 常量

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`TRACING_SESSION_SYSTEM_EVENT_FLAGS` 常量用于描述在跟踪期间要收集的系统事件。 使用它们来初始化 [TRACING_SESSION_OPTIONS](tracing-session-options-struct.md) 结构的 `SystemEventFlags` 字段。

## <a name="syntax"></a>语法

```cpp
static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT      = 0x1ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES  = 0x2ULL;

static const unsigned long long
    TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL          = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>成员

| 名称 | 此标志打开的事件 |
|--|--|
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CONTEXT` | 即使未显式指定，默认情况下此标志也会由 C++ Build Insights SDK 激活。 它使 C++ Build Insights 所需的基本系统事件正常运行。 此标志启用的事件提供有关进程、线程和图像加载的信息。 无法禁用这些事件。 |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | CPU 示例 |
| `TRACING_SESSION_SYSTEM_EVENT_FLAGS_ALL` | 此标志将打开所有系统事件。 |

::: moniker-end
