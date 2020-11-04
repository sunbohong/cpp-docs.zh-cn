---
title: FUNCTION_DATA 结构
description: C++ Build Insights SDK FUNCTION_DATA 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FUNCTION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 42dcb5a8633f0b7a6cb2fbee8a227cd3f00e2572
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920991"
---
# <a name="function_data-structure"></a>FUNCTION_DATA 结构

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`FUNCTION_DATA` 结构描述函数。

## <a name="syntax"></a>语法

```cpp
typedef struct FUNCTION_DATA_TAG
{
    const char*         Name;

} FUNCTION_DATA;
```

## <a name="members"></a>成员

| 名称 | 说明 |
|--|--|
| `Name` | 函数的名称，以 UTF-8 编码。 |

::: moniker-end
