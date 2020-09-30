---
title: 教程：Windows Performance Analyzer 基础知识
description: 有关如何在 Windows Performance Analyzer 中完成基本操作的教程。
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2d4473e3682a6e00e0eef61cb73d7450976bcc0c
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507726"
---
# <a name="tutorial-windows-performance-analyzer-basics"></a>教程：Windows Performance Analyzer 基础知识

::: moniker range="<=vs-2017"

Visual Studio 2019 中提供 C++ 生成见解工具。 若要查看此版本对应的文档，请将本文的 Visual Studio“版本”选择器控件设置为“Visual Studio 2019”。 它位于此页面上目录表的顶部。

::: moniker-end
::: moniker range="vs-2019"

需要对 Windows Performance Analyzer (WPA) 有一定的了解才能有效地使用 C++ 生成见解。 本文可帮助你熟悉常见的 WPA 操作。 有关如何使用 WPA 的详细信息，请参阅 [Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer) 文档。

## <a name="change-the-view-mode"></a>更改视图模式

WPA 提供两种基本视图模式供你浏览跟踪：

- 图形模式和
- 表模式。

可以使用“视图”窗格顶部的“视图模式”图标在它们之间切换：

![在图形模式和表模式之间切换。](media/wpa-switching-view-mode.gif)

## <a name="select-presets"></a>选择预设

大多数 C++ 生成见解 WPA 视图都有多个预设供你选择。 可以使用“视图”窗格顶部的下拉菜单来选择所需的预设：

![选择预设。](media/wpa-presets.png)

## <a name="zoom-in-and-out"></a>放大或缩小

某些生成跟踪很大，因此很难提供详细信息。 若要放大你感兴趣的区域，请右键单击图形，然后选择“缩放”。 始终可以通过选择“撤消缩放”来返回到上一个设置。 下图显示了使用选择和缩放命令对图形的一部分进行放大的示例：

![显示对图形进行放大的简短视频。](media/wpa-zooming.gif)

## <a name="group-by-different-columns"></a>按不同列分组

可以自定义跟踪的显示方式。 单击“视图”窗格顶部的齿轮图标，然后在“生成资源管理器视图编辑器”中重新排列这些列。 此对话框中的黄色行上方找到的列是对数据行进行分组所依据的列。 黄色行上方的列比较特殊：在图形视图中，它显示在彩色条上。

此图显示了链接调用的示例条形图。 我们使用齿轮图标打开“生成资源管理器视图编辑器”对话框。 然后，将“组件”和“名称”列条目拖至黄色行的上方。 更改配置以提高详细程度，并查看链接器中实际发生的情况：

![显示如何按不同列进行分组的简短视频。](media/wpa-grouping.gif)

## <a name="see-also"></a>另请参阅

[教程：vcperf 和 Windows Performance Analyzer](vcperf-and-wpa.md)\
[参考：vcperf 命令](../reference/vcperf-commands.md)\
[参考：Windows Performance Analyzer 视图](../reference/wpa-views.md)\
[Windows Performance Analyzer](/windows-hardware/test/wpt/windows-performance-analyzer)

::: moniker-end
