---
title: CALLBACK_CODE 枚举
description: C++ Build Insights SDK CALLBACK_CODE 枚举引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CALLBACK_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 146d191d0b642ad538f5a314016b41fdbdf26113
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922591"
---
# <a name="callback_code-enum"></a>CALLBACK_CODE 枚举

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`CALLBACK_CODE` 枚举用于控制分析或重新记录会话流。 返回来自 [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) 或 [RELOG_CALLBACKS](relog-callbacks-struct.md) 中的函数的 CALLBACK_CODE 值以控制接下来应执行的操作。

## <a name="members"></a>成员

| 名称 | 值 | 说明 |
|--|--|--|
| `CALLBACK_CODE_ANALYSIS_SUCCESS` | 1 (0x00000001) | 正常继续当前分析或重新记录会话。 |
| `CALLBACK_CODE_ANALYSIS_FAILURE` | 2 (0x00000002) | 取消当前分析或重新记录会话并发出错误消息。 |
| `CALLBACK_CODE_ANALYSIS_CANCEL` | 4 (0x00000004) | 取消当前分析或重新记录会话。 |

::: moniker-end
