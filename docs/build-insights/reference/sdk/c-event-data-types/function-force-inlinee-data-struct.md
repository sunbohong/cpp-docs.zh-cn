---
title: FUNCTION_FORCE_INLINEE_DATA 结构
description: C++ Build Insights SDK FUNCTION_FORCE_INLINEE_DATA 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FUNCTION_FORCE_INLINEE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d64a23c603d1f30726f30ffc91c1889c51138ef6
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041700"
---
# <a name="function_force_inlinee_data-structure"></a>FUNCTION_FORCE_INLINEE_DATA 结构

::: moniker range="<=vs-2015"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=vs-2017"

`FUNCTION_FORCE_INLINEE_DATA` 结构描述强制内联函数。

## <a name="syntax"></a>语法

```cpp
typedef struct FUNCTION_FORCE_INLINEE_DATA_TAG
{
    const char*         Name;
    unsigned short      Size;

} FUNCTION_FORCE_INLINEE_DATA;
```

## <a name="members"></a>成员

| 名称 | 说明 |
|--|--|
| `Name` | 函数的名称，以 UTF-8 编码。 |
| `Size` | 函数的大小，如中间说明数。 |

::: moniker-end
