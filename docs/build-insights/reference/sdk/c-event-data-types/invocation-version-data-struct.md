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
ms.openlocfilehash: ebed659ade4610b50ae06f2a32851522073a58d8
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923563"
---
# <a name="invocation_version_data-structure"></a>INVOCATION_VERSION_DATA 结构

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

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
