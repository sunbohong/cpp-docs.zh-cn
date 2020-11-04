---
title: SYMBOL_NAME_DATA 结构
description: C++ Build Insights SDK SYMBOL_NAME_DATA 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SYMBOL_NAME_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 08c09f304f8cc90bd48a2cecc6771d90c997a7f4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920926"
---
# <a name="symbol_name_data-structure"></a>SYMBOL_NAME_DATA 结构

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`SYMBOL_NAME_DATA` 结构描述编译器前端符号。

## <a name="syntax"></a>语法

```cpp
typedef struct SYMBOL_NAME_DATA_TAG
{
    unsigned long long  Key;
    const char*         Name;

} SYMBOL_NAME_DATA;
```

## <a name="members"></a>成员

| 名称 | 描述 |
|--|--|
| `Key` | 符号的键。 此值在要分析的跟踪中是唯一的。 |
| `Name` | 符号的名称。 |

## <a name="remarks"></a>备注

来自两个不同编译器前端传递的符号可能具有相同名称但不同的键。 在这种情况下，请使用符号名称来确定两个类型是否相同。

::: moniker-end
