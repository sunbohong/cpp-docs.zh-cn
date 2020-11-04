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
ms.openlocfilehash: 17daaa6feb784c501d180a982cd4ad2b405ccf67
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921082"
---
# <a name="event_collection_data-structure"></a>EVENT_COLLECTION_DATA 结构

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

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
