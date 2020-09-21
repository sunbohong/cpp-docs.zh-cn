---
title: FRONT_END_FILE_DATA 结构
description: C++ Build Insights SDK FRONT_END_FILE_DATA 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FRONT_END_FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c2519bfd478776f54cee59ba08b83ea00b96beff
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041752"
---
# <a name="front_end_file_data-structure"></a>FRONT_END_FILE_DATA 结构

::: moniker range="<=vs-2015"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=vs-2017"

`FRONT_END_FILE_DATA` 结构描述由编译器前端处理文件。

## <a name="syntax"></a>语法

```cpp
typedef struct FRONT_END_FILE_DATA_TAG
{
    const char*         Path;

} FRONT_END_FILE_DATA;
```

## <a name="members"></a>成员

| 名称 | 说明 |
|--|--|
| `Path` | 文件的绝对路径，以 UTF-8 编码。 |

::: moniker-end
