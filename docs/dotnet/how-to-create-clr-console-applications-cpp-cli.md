---
title: 如何：创建 CLR 控制台应用程序 (C++/CLI)
description: 了解如何创建 CLR 控制台应用项目，以便在 Visual Studio 中使用 c + +/CLI。
ms.date: 12/08/2020
helpviewer_keywords:
- console applications, templates
- CLR console applications, project template
ms.openlocfilehash: ef74ca4cc31884543ff18d63d981504f36d1838e
ms.sourcegitcommit: 754df5278f795f661d4eeb0d4cacc908aa630159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "96933217"
---
# <a name="how-to-create-clr-console-applications-ccli"></a>如何：创建 CLR 控制台应用程序 (C++/CLI)

::: moniker range="msvc-140"

您可以使用 "**新建项目**" 对话框中的 " **CLR 控制台应用程序**" 模板创建已具有基本项目引用和文件的控制台应用程序项目。

::: moniker-end
::: moniker range="msvc-150"

您可以使用 "**新建项目**" 对话框中的 " **CLR 控制台应用程序**" 模板创建已具有基本项目引用和文件的控制台应用程序项目。

安装 Visual Studio c + + 工作负荷时，默认情况下不安装 c + +/CLI 支持。 如果在 " **新建项目** " 对话框的 "Visual C++ 下看不到 CLR 标题，则可能需要安装 c + +/cli 支持。 有关详细信息，请参阅 [用 c + +/cli 进行 .net 编程](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)。

::: moniker-end
::: moniker range="msvc-160"

可以在 "**创建新项目**" 对话框中使用 **CLR 控制台应用 ( .NET Framework)** 模板创建已具有基本项目引用和文件的控制台应用程序项目。

安装 Visual Studio c + + 工作负荷时，默认情况下不安装 c + +/CLI 支持。 如果在 "  **创建新项目** " 对话框中看不到 "CLR 项目模板"，可能需要安装 c + +/cli 支持。 有关详细信息，请参阅 [用 c + +/cli 进行 .net 编程](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)。

::: moniker-end

通常，控制台应用程序被编译为独立的可执行文件，但它没有图形用户界面。 用户在命令提示符处运行控制台应用程序。 它们可以使用命令行向正在运行的应用程序发出指令。 应用程序在命令窗口中以文本形式提供输出信息。 控制台应用的即时反馈使其成为了解编程的好方法。 无需担心如何实现图形用户界面。

::: moniker range="msvc-140"

使用 CLR 控制台应用程序模板创建项目时，它会自动添加以下引用和文件：

- 以下 .NET Framework 命名空间的参考信息：

  - <xref:System>、 <xref:System.Data> 、 <xref:System.Xml> ：这些引用包含定义常用类型、事件、接口、属性和异常的基本类。

  - *`mscorlib.dll`*：支持 .NET Framework 开发的程序集 DLL。

- 源文件：

  - *`ConsoleApplicationName.cpp`*：主源文件和应用程序的入口点。 此文件具有你为项目指定的基名称。 它标识项目 DLL 文件和项目命名空间。 在此文件中提供你自己的代码。

  - *`AssemblyInfo.cpp`*：包含可用于修改项目的程序集元数据的属性和设置。 有关详细信息，请参阅 [程序集内容](/dotnet/framework/app-domains/assembly-contents)。

  - *`stdafx.cpp`*：用于生成名为的预编译标头文件 *`ConsoleApplicationName.pch`* 和名为的预编译类型文件 *`stdafx.obj`* 。

- 头文件：

  - *`stdafx.h`*：用于生成名为的预编译标头文件 *`ConsoleApplicationName.pch`* 和名为的预编译类型文件 *`stdafx.obj`* 。

  - *`resource.h`*：生成的包含文件 *`app.rc`* 。

- 资源文件：

  - *`app.rc`*：程序的资源脚本文件。

  - *`app.ico`*：程序的图标文件。

- *`ReadMe.txt`*：描述项目中的文件。

::: moniker-end
::: moniker range=">=msvc-150"

使用 CLR 控制台应用程序模板创建项目时，它会自动添加以下引用和文件：

- 以下 .NET Framework 命名空间的参考信息：

  - <xref:System>、 <xref:System.Data> 、 <xref:System.Xml> ：这些引用包含定义常用类型、事件、接口、属性和异常的基本类。

  - *`mscorlib.dll`*：支持 .NET Framework 开发的程序集 DLL。

- 源文件：

  - *`ConsoleApplicationName.cpp`*：主源文件和应用程序的入口点。 此文件具有你为项目指定的基名称。 它标识项目 DLL 文件和项目命名空间。 在此文件中提供你自己的代码。

  - *`AssemblyInfo.cpp`*：包含可用于修改项目的程序集元数据的属性和设置。 有关详细信息，请参阅 [程序集内容](/dotnet/framework/app-domains/assembly-contents)。

  - *`pch.cpp`*：用于生成名为的预编译标头文件 *`ConsoleApplicationName.pch`* 和名为的预编译类型文件 *`pch.obj`* 。

- 头文件：

  - *`pch.h`*：用于生成名为的预编译标头文件 *`ConsoleApplicationName.pch`* 和名为的预编译类型文件 *`pch.obj`* 。

  - *`Resource.h`*：生成的包含文件 *`app.rc`* 。

- 资源文件：

  - *`app.rc`*：程序的资源脚本文件。

  - *`app.ico`*：程序的图标文件。

::: moniker-end

## <a name="to-create-a-clr-console-app-project"></a>创建 CLR 控制台应用项目

::: moniker range="msvc-140"

1. 在菜单栏上，依次选择“文件”  >“新建”  >“项目”  。

1. 在 " **新建项目** " 对话框中，选择 " **已安装** 的 > **模板** > **Visual C++** > **CLR** " 节点，然后选择 " **clr 控制台应用程序** " 模板。

1. 在“名称”  框中，输入你的应用程序的唯一名称。

   你可以指定其他项目和解决方案设置，但它们不是必需的。

1. 选择 " **确定"** 按钮以生成项目和源文件。

::: moniker-end
::: moniker range="msvc-150"

1. 在菜单栏上，依次选择“文件”  >“新建”  >“项目”  。

1. 在 " **新建项目** " 对话框中，选择 " **已安装** 的 > **Visual C++** > **clr** " 节点，然后选择 " **clr 控制台" 应用程序** 模板。

1. 在“名称”  框中，输入你的应用程序的唯一名称。

   你可以指定其他项目和解决方案设置，但它们不是必需的。

1. 选择 " **确定"** 按钮以生成项目和源文件。

::: moniker-end
::: moniker range="msvc-160"

1. 在菜单栏上，依次选择“文件”  >“新建”  >“项目”  。

1. 在 " **创建新项目** " 对话框中，在搜索框中输入 "clr 控制台"。 选择 **CLR 控制台应用 ( .NET Framework)** 模板，然后选择 " **下一步**"。

1. 在“名称”  框中，输入你的应用程序的唯一名称。

   你可以指定其他项目和解决方案设置，但它们不是必需的。

1. 选择 " **创建** " 按钮以生成项目和源文件。

::: moniker-end

## <a name="see-also"></a>另请参阅

[CLR 项目](../build/reference/files-created-for-clr-projects.md)
