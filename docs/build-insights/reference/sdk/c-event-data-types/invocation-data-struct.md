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
ms.openlocfilehash: 98ac234b702ef2c73a5c8d90ee6bf4dc59349ed6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920965"
---
# <a name="invocation_data-structure"></a>INVOCATION_DATA 结构

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

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
