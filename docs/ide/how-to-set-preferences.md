---
description: 详细了解：在 Visual Studio 中设置 C++ 代码首选项
title: 在 Visual Studio 中设置 C++ 代码首选项
ms.description: Customize C++ formatting, colors, layout, line numbers, and menus in the Visual Studio IDE.
ms.topic: overview
ms.date: 09/27/2019
ms.openlocfilehash: 9a82c0771c097bb1246737f748077bbc303ac9f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240905"
---
# <a name="set-your-c-coding-preferences-in-visual-studio"></a>在 Visual Studio 中设置 C++ 代码首选项

你可以通过个性化设置 Visual Studio 来使 C++ 编码体验更方便、更高效且更愉悦。 方法：

- 自定义菜单和工具栏。
- 排列窗口布局。
- 设置颜色主题。
- 指定 C++ 格式设置规则，包括多个 ClangFormat 样式。
- 创建自定义键盘快捷方式。

可以跨多台计算机同步首选项，创建和存储多组首选项，并与团队成员共享这些首选项。 可以从 Visual Studio Marketplace 安装扩展，从而提供用于自定义行为的其他选项。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。

## <a name="arrange-window-layout"></a>排列窗口布局

在 Visual Studio 窗口中，空间划分为主菜单、工具栏、代码编辑器（或文档窗口）和工具窗口（如解决方案资源管理器和错误列表）。 某些窗口在同一位置相互重叠。 例如，解决方案资源管理器、类视图、资源视图和源代码管理器均共享同一默认位置。 通过选择框架底部的选项卡，可以在这些选项卡之间进行切换。 若要使两个或更多窗口同时可见，只需将其中一个窗口的标题栏拖到新位置即可。 可以将其停靠在其中一个 Visual Studio 主窗口边框上，也可以使其浮动。

以下屏幕截图显示“团队资源管理器”窗口，将从其默认位置拖动到代码编辑器左侧的新停靠位置。 蓝色阴影区域显示在释放鼠标按钮时将放置窗口的位置。

![“Visual Studio 团队资源管理器”窗口的屏幕截图，其中突出显示了布局更改](media/window-layout-move-team-explorer.png)

在文档窗口中，每个打开的文件都包含在选项卡式框架中。 可以浮动或锁定这些选项卡，就像工具窗口一样。 有关详细信息，请参阅[在 Visual Studio 中自定义窗口布局](/visualstudio/ide/customizing-window-layouts-in-visual-studio)。

若要隐藏所有工具窗口并最大化“代码编辑器”窗口，请按 Alt + Shift + Enter 以切换全屏模式。

## <a name="set-c-coding-styles-and-formatting"></a>设置 C++ 编码样式和格式设置

可以指定许多单个代码格式设置选项，如缩进和括号位置。 为此，请转到“工具” > “选项” > “文本编辑器” > “C/C++” > “格式设置”（或键入 Ctrl + Q 并搜索“格式设置”）。 或者，可以指定 [ClangFormat](https://clang.llvm.org/docs/ClangFormat.html) 样式之一（或你自己的自定义 ClangFormat 样式）。

![ClangFormat 选项的屏幕截图](media/clang-format-ide.png)

有关所有格式设置选项的详细信息，请参阅[选项、文本编辑器、C/C++、格式设置](/visualstudio/ide/reference/options-text-editor-c-cpp-formatting)。

## <a name="set-the-color-theme"></a>设置颜色主题

若要设置浅色或深色背景，请键入 Ctrl + Q 并搜索“颜色主题”。 还可以通过转到“工具” > “选项” > “环境”，然后选择“颜色主题”来查找。

![颜色主题的屏幕截图](media/tools-options-color-theme.png)

例如，下面是深色主题：

![具有深色主题的 Visual Studio 的屏幕截图](media/tools-options-dark-theme.png)

## <a name="customize-code-colorization"></a>自定义代码着色

在 Visual Studio 2019 中，可以从三个预定义的配色方案中进行选择。 这些方案指定如何在编辑器中对代码元素进行着色。 若要选择主题，请转到“工具” > “选项” > “文本编辑器” > “C/C++” > “视图”，然后选择“配色方案”：

![突出显示“增强”的配色方案选项的屏幕截图](media/color-schemes.png)

在名为“Visual Studio 2017”的配色方案中，大多数代码元素只是黑色。 在“增强”配色方案中，对函数、局部变量、宏和其他元素进行了着色。 在“增强(全局与成员)方案中，对全局函数和变量进行着色以与类成员形成对比。 默认模式为“增强”，如下所示：

![“增强”配色方案的屏幕截图](media/color-scheme-enhanced.png)

无论使用哪个主题或配色方案，都可以为单个代码元素自定义字体和颜色。 为此，请转到“工具” > “选项” > “环境” > “字体和颜色”（或键入 Ctrl + Q 并搜索“字体”）。 向下滚动显示项的列表，直到看到 C++ 选项。

![C++ 字体和颜色选项的屏幕截图](media/tools-options-cpp-colors.png)

此处设置的颜色将覆盖为配色方案定义的值。 如果要恢复配色方案的默认颜色，请将颜色设置回“默认”。

## <a name="customize-the-toolbars"></a>自定义工具栏

使用工具栏，只需单击一次（而不是使用菜单或键盘快捷方式）即可轻松发出命令。 Visual Studio 包含一组标准工具栏。 对于标准 C++ 开发，最有用的工具栏可能是“标准”、“文本编辑器”、“生成”、“调试”、“源代码管理”和“比较文件”。 对于 Windows 开发，“对话框编辑器”和“图像编辑器”对于布局对话框和编辑图标很有用。

将鼠标悬停在工具栏中的图标上，以查看它代表哪个命令：

![悬停时可显示命令信息示例的的工具栏图标的屏幕截图](media/toolbar-mouse-hover.png)

可以通过选择向下箭头来添加或删除命令，或创建自定义工具栏。 若要将工具栏移动到新位置，请拖动左侧的虚线栏。

![突出显示向下箭头和虚线栏的工具栏的屏幕截图](media/toolbar-move-edit.png).

有关详细信息，请参阅[如何：在 Visual Studio 中自定义菜单和工具栏](/visualstudio/ide/how-to-customize-menus-and-toolbars-in-visual-studio)。

## <a name="show-or-hide-line-numbers"></a>显示或隐藏行号

可以指定行号是否显示在编辑器窗口的左侧。 在“选项”的“C/C++”下，选择“常规”。 在“设置”部分中，根据你的首选项选择或清除“行号”。

![突出显示行号的“常规”选项的屏幕截图](media/tools-options-line-numbers.png)

## <a name="create-keyboard-shortcuts"></a>创建键盘快捷方式

Visual Studio 中的许多命令都具有键盘快捷方式，以及包含 Ctrl、Alt 和 Shift 键的键组合。 可以在 Visual Studio 中修改这些键盘快捷方式或创建自己的新键盘快捷方式。 转到“工具” > “选项” > “环境” > “键盘”（或键入 Ctrl + Q 并搜索“快捷方式”）。 有关详细信息，请参阅[在 Visual Studio 中标识并自定义键盘快捷方式](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)。
