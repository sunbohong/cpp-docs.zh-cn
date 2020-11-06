---
title: TEMPLATE_INSTANTIATION_KIND_CODE 枚举
description: C++ Build Insights SDK TEMPLATE_INSTANTIATION_KIND_CODE 枚举引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_KIND_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2ee85af4e3d7f19b1b5dc9163dab6090f5ce4e42
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920939"
---
# <a name="template_instantiation_kind_code-enum"></a>TEMPLATE_INSTANTIATION_KIND_CODE 枚举

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`TEMPLATE_INSTANTIATION_KIND_CODE` 枚举。

## <a name="members"></a>成员

| 名称 | 值 | 说明 |
|--|--|--|
| `TEMPLATE_INSTANTIATION_KIND_CODE_CLASS` | 0 (0x00000000) | 类模板实例化。 |
| `TEMPLATE_INSTANTIATION_KIND_CODE_FUNCTION` | 1 (0x00000001) | 函数模板实例化。 |
| `TEMPLATE_INSTANTIATION_KIND_CODE_VARIABLE` | 2 (0x00000002) | constexpr 变量实例化。 |
| `TEMPLATE_INSTANTIATION_KIND_CODE_CONCEPT` | 3 (0x00000003) | 概念模板实例化。 |

## <a name="remarks"></a>备注

::: moniker-end
