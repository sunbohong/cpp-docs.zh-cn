---
title: AnalysisControl 枚举类
description: C++ Build Insights SDK AnalysisControl 枚举引用。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalysisControl
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 0f4887d626c5e80a0afaa393e255f8ffedbd6b1f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922618"
---
# <a name="analysiscontrol-enum-class"></a>AnalysisControl 枚举类

::: moniker range="<=msvc-140"

C++ Build Insights SDK 与 Visual Studio 2017 及更高版本兼容。 若要查看这些版本的文档，请将本文的 Visual Studio“版本”选择器控件设置为 Visual Studio 2017 或 Visual Studio 2019。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range=">=msvc-150"

`AnalysisControl` 枚举类用于控制分析或重新记录会话流。 从 [IAnalyzer](ianalyzer-class.md) 或 [IRelogger](irelogger-class.md) 成员函数返回 `AnalysisControl` 代码，以控制接下来应执行的操作。

## <a name="members"></a>成员

| 名称 | 描述 |
|--|--|
| `BLOCK` | 防止当前事件在分析器或重新记录器组中进一步传播。 |
| `CANCEL` | 取消当前分析或重新记录会话。 |
| `CONTINUE` | 正常继续当前分析或重新记录会话。 将当前事件传播到下一个分析器或重新记录器组成员。 |
| `FAILURE` | 取消当前分析或重新记录会话并发出错误消息。 |

::: moniker-end
