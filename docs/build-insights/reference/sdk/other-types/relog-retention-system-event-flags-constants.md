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
ms.openlocfilehash: 5444c1a6b8799b1de8eea228211a5f2d6de638f8
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041401"
---
# <a name="relog_retention_system_event_flags-constants"></a>RELOG_RETENTION_SYSTEM_EVENT_FLAGS 常数

::: moniker range="<=vs-2015"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=vs-2017"

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
