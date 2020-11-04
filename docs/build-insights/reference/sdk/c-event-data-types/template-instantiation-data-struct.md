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
ms.openlocfilehash: c92fbd8ee7e1fff702757d003ab3bbe0bdabd886
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923434"
---
# <a name="template_instantiation_data-structure"></a>TEMPLATE_INSTANTIATION_DATA 结构

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

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
