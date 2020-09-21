---
title: INVOCATION_VERSION_DATA 结构
description: C++ Build Insights SDK INVOCATION_VERSION_DATA 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_VERSION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ec54c560dd408dc3beecbc20eaac69d389c7ec37
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041554"
---
# <a name="invocation_version_data-structure"></a>INVOCATION_VERSION_DATA 结构

::: moniker range="<=vs-2015"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=vs-2017"

`INVOCATION_VERSION_DATA` 结构描述作为一组整数值的版本号。

## <a name="syntax"></a>语法

```cpp
typedef struct INVOCATION_VERSION_DATA_TAG
{
    unsigned short VersionMajor;
    unsigned short VersionMinor;
    unsigned short BuildNumberMajor;
    unsigned short BuildNumberMinor;

} INVOCATION_VERSION_DATA;
```

## <a name="members"></a>成员

| 名称 | 说明 |
|--|--|
| `VersionMajor` | 版本的主要版本号。 |
| `VersionMinor` | 版本的次要版本号。 |
| `BuildNumberMajor` | 生成的主要版本号。 |
| `BuildNumberMinor` | 生成的次要版本号。 |

::: moniker-end
