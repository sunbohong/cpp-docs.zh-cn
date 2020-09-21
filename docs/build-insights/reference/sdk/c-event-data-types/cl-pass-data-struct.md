---
title: CL_PASS_DATA 结构
description: C++ Build Insights SDK CL_PASS_DATA 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CL_PASS_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 52ee5fdaae12784c2f59d2c47ac9a2fd80649f27
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040530"
---
# <a name="cl_pass_data-structure"></a>CL_PASS_DATA 结构

::: moniker range="<=vs-2015"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=vs-2017"

`CL_PASS_DATA` 结构描述编译传递。

## <a name="syntax"></a>语法

```cpp
typedef struct CL_PASS_DATA_TAG
{
    int                         TranslationUnitPassCode;
    const wchar_t*              InputSourcePath;
    const wchar_t*              OutputObjectPath;

} CL_PASS_DATA;
```

## <a name="members"></a>成员

| 名称 | 说明 |
|--|--|
| `TranslationUnitPassCode` | 标识要执行的编译传递的代码。 有关详细信息，请参阅 [TRANSLATION_UNIT_PASS_CODE](translation-unit-pass-code-enum.md)。 |
| `InputSourcePath` | 正在执行此编译传递的 C 或 C++ 源文件。 |
| `OutputObjectPath` | 编译器生成的对象文件。 |

::: moniker-end
