---
title: 使用 C++/CLI 进行 .NET 编程
description: 了解如何使用 c + +/CLI 在 Visual Studio 中创建 .NET 应用程序和组件。
ms.date: 12/08/2020
helpviewer_keywords:
- programming [C++], .NET programming
- .NET Framework [C++]
- .NET applications [C++]
- Visual C++, .NET programming
ms.openlocfilehash: 80a9743016976e307158608134155dc7272d44a8
ms.sourcegitcommit: 754df5278f795f661d4eeb0d4cacc908aa630159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96933178"
---
# <a name="net-programming-with-ccli"></a>使用 C++/CLI 进行 .NET 编程

::: moniker range="msvc-140"

默认情况下，使用 Visual Studio 2015 创建的 CLR 项目将以.NET Framework 4.5.2 为目标。 创建新项目时，可以将 .NET Framework 4.6 设定为目标。 在 " **新建项目** " 对话框中，更改对话框顶部中间的下拉列表中的目标框架。 若要更改现有项目的目标框架，请关闭项目，编辑项目文件 (*`.vcxproj`*) ，并将目标 Framework 版本的值更改为4.6。 更改将在下次打开该项目时生效。

::: moniker-end
::: moniker range="msvc-150"

在 Visual Studio 2017 中，默认目标 .NET Framework 是4.6.1。 框架版本选择器位于 " **新建项目** " 对话框的底部。

## <a name="install-ccli-support-in-visual-studio-2017"></a>在 Visual Studio 2017 中安装 c + +/CLI 支持

安装 Visual Studio c + + 工作负荷时，默认情况下不安装 c + +/CLI 本身。 若要在安装 Visual Studio 后安装组件，请打开 Visual Studio 安装程序。 选择已安装的 Visual Studio 版本旁边的 " **修改** " 按钮。 选择 " **已安装的组件** " 选项卡。向下滚动到 " **编译器、生成工具和运行时** " 部分，然后选择 " **c + +/cli 支持**"。 选择 " **修改** " 以更新 Visual Studio。

::: moniker-end
::: moniker range="msvc-160"

在 Visual Studio 2019 中，.NET Core 项目的默认目标框架是5.0。 对于 .NET Framework 项目，默认值为4.7.2。 .NET Framework 版本选择器位于 "新建 **项目**" 对话框的 "**配置新项目**" 页上。
## <a name="install-ccli-support-in-visual-studio-2019"></a>在 Visual Studio 2019 中安装 c + +/CLI 支持

安装 Visual Studio c + + 工作负荷时，默认情况下不安装 c + +/CLI 本身。 若要在安装 Visual Studio 后安装组件，请打开 Visual Studio 安装程序。 选择已安装的 Visual Studio 版本旁边的 " **修改** " 按钮。 选择 " **已安装的组件** " 选项卡。向下滚动到 " **编译器"、"生成工具" 和 "运行时** " 部分，并选择最新的 **c + +/cli 支持 "v142 生成工具** " 组件。 选择 " **修改** " 以更新 Visual Studio。

::: moniker-end

## <a name="in-this-section"></a>在本节中

[C++/CLI 任务](../dotnet/cpp-cli-tasks.md)

[本机和 .NET 的互操作性](../dotnet/native-and-dotnet-interoperability.md)

[纯代码和可验证代码 (c + +/CLI) ](../dotnet/pure-and-verifiable-code-cpp-cli.md)

[C + +/CLI)  (正则表达式 ](../dotnet/regular-expressions-cpp-cli.md)

[C + +/CLI) 的文件处理和 i/o (](../dotnet/file-handling-and-i-o-cpp-cli.md)

[ (c + +/CLI) 的图形操作 ](../dotnet/graphics-operations-cpp-cli.md)

[Windows operations (c + +/CLI) ](../dotnet/windows-operations-cpp-cli.md)

[使用 ADO.NET (c + +/CLI) 进行数据访问 ](../dotnet/data-access-using-adonet-cpp-cli.md)

[与其他 .NET 语言的互操作性 (c + +/CLI) ](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)

[序列化 (C++/CLI)](../dotnet/serialization-cpp-cli.md)

[C + +/CLI (托管类型) ](../dotnet/managed-types-cpp-cli.md)

[反射 (C++/CLI)](../dotnet/reflection-cpp-cli.md)

[强名称程序集 (程序集签名)  (c + +/CLI) ](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)

[Debug 类 (c + +/CLI) ](../dotnet/debug-class-cpp-cli.md)

[STL/CLR 库参考](../dotnet/stl-clr-library-reference.md)

[C++ 支持库](../dotnet/cpp-support-library.md)

[C++/CLI 中的异常](../dotnet/exceptions-in-cpp-cli.md)

[装箱 (C++/CLI)](../dotnet/boxing-cpp-cli.md)

## <a name="see-also"></a>另请参阅

[本机和 .NET 的互操作性](../dotnet/native-and-dotnet-interoperability.md)
