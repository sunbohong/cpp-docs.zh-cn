---
description: 详细了解：操作说明：修改目标框架和平台工具集
title: 如何：修改目标框架和平台工具集
ms.custom: conceptual
ms.date: 07/24/2019
helpviewer_keywords:
- 'msbuild (c++), howto: modify target framework and platform toolset'
ms.assetid: 031b1d54-e6e1-4da7-9868-3e75a87d9ffe
ms.openlocfilehash: 8b3de299652efcdd8fd94622b890b6cec7b059e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156250"
---
# <a name="how-to-modify-the-target-framework-and-platform-toolset"></a>如何：修改目标框架和平台工具集

可以编辑 Visual Studio C++ 项目文件以面向不同版本的 C++ 平台工具集、Windows SDK 和 .NET Framework（仅限 C++/CLI 项目）。 默认情况下，项目系统将使用对应于你用于创建该项目的 Visual Studio 版本的 .NET Framework 版本和工具集版本。 可以在 .vcxproj 文件中修改所有这些值，以便可以对每个编译目标使用相同的基本代码。

## <a name="platform-toolset"></a>平台工具集

平台工具集包含 C++ 编译器 (cl.exe) 和链接器 (link.exe) 以及 C/C++ 标准库。 自 Visual Studio 2015 起，工具集的主版本保持为 14，这意味着使用 Visual Studio 2019 或 Visual Studio 2017 编译的项目在 ABI 方面向后兼容于使用 Visual Studio 2015 编译的项目。 自 Visual Studio 2015 以来，次版本对于每个版本都按 1 更新：

- Visual Studio 2015：v140
- Visual Studio 2017：v141
- Visual Studio 2019：v142

这些工具集支持 .NET Framework 4.5 及更高版本。

Visual Studio 还对 C++ 项目支持多定向。 可以使用 Visual Studio IDE 编辑和生成使用较旧版本的 Visual Studio 创建的项目，而无需将它们升级为使用新版本的工具集。 需要在计算机上安装较旧的工具集。 有关详细信息，请参阅[如何在 Visual Studio 中使用本机多定向](../porting/use-native-multi-targeting.md)。 例如，在 Visual Studio 2015 中，可以面向  .NET Framework 2.0，但必须使用支持它的早期工具集。

## <a name="target-framework-ccli-project-only"></a>目标框架（仅限 C++/CLI 项目）

在更改目标 Framework 时，也要将平台工具集更改为支持该 Framework 的版本。 例如，要面向 .NET Framework 4.5，你必须使用兼容平台工具集，例如 Visual Studio 2015 (v140)、Visual Studio 2013 (v120) 或 Visual Studio 2012 (v110)。 可以使用 [Windows 7.1 SDK](https://www.microsoft.com/download/details.aspx?id=8279) 平台工具集面向 .NET Framework 2.0、3.0、3.5 和 4 以及 x86/x64 平台。

可以通过创建自定义平台工具集来扩展目标平台。 有关详细信息，请参见 Visual C++ 博客上的 [C++ 本机多目标](https://devblogs.microsoft.com/cppblog/c-native-multi-targeting/) 。

### <a name="to-change-the-target-framework"></a>更改目标框架

1. 在 Visual Studio 中，在“解决方案资源管理器”  中，选择你的项目。 在菜单栏上，打开“项目”  菜单并选择“卸载项目”  。 这将为你的项目卸载项目文件 (.vcxproj)。

   > [!NOTE]
   >  C++ 项目文件正在 Visual Studio 中修改时无法加载该项目。 但是，当项目加载到 Visual Studio 中时，你可以使用另一个编辑器（如记事本）来修改项目文件。 Visual Studio 会检测到项目文件的更改并提示你重新加载项目。

1. 在菜单栏上，依次选择 **“文件”** 、 **“打开”** 、 **“文件”** 。 在 **“打开文件”** 对话框中，导航到项目文件夹，然后打开项目文件 (.vcxproj)。

1. 在项目文件中，找到目标 Framework 版本的条目。 例如，如果你的项目设计为使用 .NET Framework 4.5，请在 `<TargetFrameworkVersion>v4.5</TargetFrameworkVersion>` 元素的 `<PropertyGroup Label="Globals">` 元素中找到 `<Project>` 。 如果 `<TargetFrameworkVersion>` 元素不存在，你的项目不使用 .NET Framework，也无需进行更改。

1. 将值更改为需要的 Framework 版本，例如 v3.5 或 v4.6。

1. 保存更改并关闭编辑器。

1. 在 **“解决方案资源管理器”** 中，打开项目的快捷菜单，然后选择 **“重新加载项目”** 。

1. 若要验证更改，在“解决方案资源管理器”  中，右键单击打开你的项目（不适用于解决方案）的快捷菜单，然后选择“属性”  以打开项目“属性页”  对话框。 在对话框的左窗格中，展开 **“配置属性”** ，然后选择 **“常规”** 。 验证“.NET 目标 Framework 版本”  是否显示了新的 Framework 版本。

### <a name="to-change-the-platform-toolset"></a>更改平台工具集

1. 在 Visual Studio 中，在 **解决方案资源管理器** 中，打开您的项目（不适用于您的解决方案）的快捷菜单，然后选择 **属性** 可打开 **项目属性页** 对话框。

1. 在 **“属性页”** 对话框中，打开 **“配置”** 下拉列表，然后选择 **“所有配置”** 。

1. 在对话框的左窗格中，展开 **“配置属性”** ，然后选择 **“常规”** 。

1. 在右窗格中，选择 **“平台工具集”** ，然后从下拉列表中选择需要的工具集。 例如，如果已安装了 Visual Studio 2010 工具集，请选择“Visual Studio 2010 (v100)”  以用于项目。

1. 选择“确定”  按钮。

## <a name="see-also"></a>请参阅

[命令行上的 MSBuild - C++](msbuild-visual-cpp.md)
