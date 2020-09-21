---
title: TEMPLATE_INSTANTIATION_DATA 结构
description: C++ Build Insights SDK TEMPLATE_INSTANTIATION_DATA 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 15bbb25c3abac339201179e763bffd916dba0480
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040868"
---
# <a name="template_instantiation_data-structure"></a>TEMPLATE_INSTANTIATION_DATA 结构

::: moniker range="<=vs-2015"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=vs-2017"

`TEMPLATE_INSTANTIATION_DATA` 结构描述了模板实例化。

## <a name="syntax"></a>语法

```cpp
typedef struct TEMPLATE_INSTANTIATION_DATA_TAG
{
    unsigned long long  SpecializationSymbolKey;
    unsigned long long  PrimaryTemplateSymbolKey;
    int                 KindCode;

} TEMPLATE_INSTANTIATION_DATA;
```

## <a name="members"></a>成员

| 名称 | 描述 |
|--|--|
| `SpecializationSymbolKey` | 模板专用化类型的键。 此值在要分析的跟踪中是唯一的。 |
| `PrimaryTemplateSymbolKey` | 专用化的主模板类型的键。 此值在要分析的跟踪中是唯一的。 |
| `KindCode` | 模板实例化的类型。 有关详细信息，请参阅 [TEMPLATE_INSTANTIATION_KIND_CODE](template-instantiation-kind-code-enum.md)。 |

## <a name="remarks"></a>备注

`TEMPLATE_INSTANTIATION_DATA` 结构中的键在要分析的跟踪中是唯一的。 不过，来自不同编译器前端传递的两个不同键可能指向两个相同的类型。 当使用来自多个编译器前端传递的 `TEMPLATE_INSTANTIATION_DATA` 信息时，请使用 [SYMBOL_NAME](../event-table.md#symbol-name) 事件确定两个类型是否相同。 `SymbolName` 事件在编译器前端传递结束时发出（在所有模板实例化发生后）。

::: moniker-end
