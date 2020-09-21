---
title: INVOCATION_DATA 结构
description: C++ Build Insights SDK INVOCATION_DATA 结构参考。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 48b4c28d3c01d61a31343894312a54ba2ab17a70
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041635"
---
# <a name="invocation_data-structure"></a>INVOCATION_DATA 结构

::: moniker range="<=vs-2015"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=vs-2017"

`INVOCATION_DATA` 结构描述编译器或链接器调用。

## <a name="syntax"></a>语法

```cpp
typedef struct INVOCATION_DATA_TAG
{
    int                         MSVCToolCode;

    INVOCATION_VERSION_DATA     ToolVersion;

    const char*                 ToolVersionString;
    const wchar_t*              WorkingDirectory;
    const wchar_t*              ToolPath;

} INVOCATION_DATA;
```

## <a name="members"></a>成员

| 名称 | 说明 |
|--|--|
| `MSVCToolCode` | 标识调用的类型的代码。 有关详细信息，请参阅 [MSVC_TOOL_CODE](msvc-tool-code-enum.md)。 |
| `ToolVersion` | 将已调用的工具的版本存储为一组整数值的对象。 |
| `ToolVersionString` | 以文本形式描述已调用的工具的版本。 |
| `WorkingDirectory` | 从中进行调用的目录。 |
| `ToolPath` | 已调用的工具的绝对路径。 |

::: moniker-end
