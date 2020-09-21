---
title: EVENT_COLLECTION_DATA 结构
description: C++ Build Insights SDK EVENT_COLLECTION_DATA 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_COLLECTION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 58be46d31af154bfe7ecef5c440092eaafdcbb0f
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039594"
---
# <a name="event_collection_data-structure"></a>EVENT_COLLECTION_DATA 结构

::: moniker range="<=vs-2015"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=vs-2017"

`EVENT_COLLECTION_DATA` 结构描述 [EVENT_DATA](event-data-struct.md) 元素的数组。

## <a name="syntax"></a>语法

```cpp
typedef struct EVENT_COLLECTION_DATA_TAG
{
    unsigned int            Count;
    const EVENT_DATA*       Elements;

} EVENT_COLLECTION_DATA;
```

## <a name="members"></a>成员

| 名称 | 说明 |
|--|--|
| `Count` | 数组中的 `EVENT_DATA` 元素数。 |
| `Elements` | 指向数组中第一个 `EVENT_DATA` 元素的指针。 |

::: moniker-end
