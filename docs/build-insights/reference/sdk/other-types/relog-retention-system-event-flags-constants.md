---
title: RELOG_RETENTION_SYSTEM_EVENT_FLAGS 常数
description: C++ Build Insights SDK RELOG_RETENTION_SYSTEM_EVENT_FLAGS 常数引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_RETENTION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e0144835568dab12c8593fe8fbfa820f6cde7647
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919722"
---
# <a name="relog_retention_system_event_flags-constants"></a>RELOG_RETENTION_SYSTEM_EVENT_FLAGS 常数

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`RELOG_RETENTION_SYSTEM_EVENT_FLAGS` 常数用于描述要保存在重新记录的跟踪中的系统事件。 使用它们初始化 [RELOG_DESCRIPTOR](relog-descriptor-struct.md) 结构的 `SystemEventsRetentionFlags` 字段。

## <a name="syntax"></a>语法

```cpp
static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES = 0x1ULL;

static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL         = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>成员

| 名称 | 描述 |
|--|--|
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | 在重新记录的跟踪中保留 CPU 示例系统事件。 |
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL` | 在重新记录的跟踪中保留所有系统事件。 |

## <a name="remarks"></a>备注

::: moniker-end
