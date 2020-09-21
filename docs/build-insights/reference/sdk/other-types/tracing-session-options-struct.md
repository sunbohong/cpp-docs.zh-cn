---
title: TRACING_SESSION_OPTIONS 结构
description: C++ Build Insights SDK TRACING_SESSION_OPTIONS 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_OPTIONS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c8a248d884b5232fbc5332db1a68533220ef2fab
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041258"
---
# <a name="tracing_session_options-structure"></a>TRACING_SESSION_OPTIONS 结构

::: moniker range="<=vs-2015"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=vs-2017"

初始化 [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) 或 [RELOG_DESCRIPTOR](relog-descriptor-struct.md) 结构时使用 `TRACING_SESSION_OPTIONS` 结构。 它描述在跟踪的收集过程中要捕获的事件。

## <a name="syntax"></a>语法

```cpp
typedef struct TRACING_SESSION_OPTIONS_TAG
{
    unsigned long long SystemEventFlags;
    unsigned long long MsvcEventFlags;

} TRACING_SESSION_OPTIONS;
```

## <a name="members"></a>成员

| 名称 | 描述 |
|--|--|
| `SystemEventFlags` | 一个位掩码，描述要捕获的系统事件。 有关详细信息，请参阅 [TRACING_SESSION_SYSTEM_EVENT_FLAGS](tracing-session-system-event-flags-constants.md)。 |
| `MsvcEventFlags` | 一个位掩码，描述要捕获的 MSVC 事件。 有关详细信息，请参阅 [TRACING_SESSION_MSVC_EVENT_FLAGS](tracing-session-msvc-event-flags-constants.md)。 |

::: moniker-end
