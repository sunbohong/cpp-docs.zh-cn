---
title: MSVC_TOOL_CODE 枚举
description: C++ Build Insights SDK MSVC_TOOL_CODE 枚举引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MSVC_TOOL_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4f539401f304d5d39983ec8f97cc8c99b19399d9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920952"
---
# <a name="msvc_tool_code-enum"></a>MSVC_TOOL_CODE 枚举

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`MSVC_TOOL_CODE` 枚举。

## <a name="members"></a>成员

| 名称 | 值 | 说明 |
|--|--|--|
| `MSVC_TOOL_CODE_CL` | 0 (0x00000000) | 编译器 (cl.exe)。 |
| `MSVC_TOOL_CODE_LINK` | 1 (0x00000001) | 链接器 (link.exe)。 |

## <a name="remarks"></a>注解

由 C SDK 函数使用。

::: moniker-end
