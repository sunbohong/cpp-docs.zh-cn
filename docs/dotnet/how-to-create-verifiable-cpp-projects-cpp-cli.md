---
description: '了解详细信息：如何：创建可验证的 c + + 项目 (c + +/CLI) '
title: 如何：创建可验证的 C++ 项目 (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- verifiable assemblies [C++], creating
- conversions, C++ projects
- Visual Studio C++ projects
ms.assetid: 4ef2cc1a-e3e5-4d67-8d8d-9c614f8ec5d3
ms.openlocfilehash: 5f3a84a4f87db5cf390dcfbad18f167108e0ff08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245988"
---
# <a name="how-to-create-verifiable-c-projects-ccli"></a>如何：创建可验证的 c + + 项目 (c + +/CLI) 

Visual C++ 应用程序向导不会创建可验证项目。

> [!IMPORTANT]
> Visual Studio 2015 已弃用，并且 Visual Studio 2017 不支持 **/clr： pure** 和 **/clr：** 可验证项目的安全创建。 如果需要可验证代码，建议将代码转换为 c #。

但是，如果您使用的是支持 **/clr： pure** 和 **/clr： safe** 的较早版本的 Microsoft c + + 编译器工具集，则项目可以转换为可验证。 本主题介绍如何设置项目属性并修改项目源文件，以转换 Visual Studio c + + 项目以生成可验证的应用程序。

## <a name="compiler-and-linker-settings"></a>编译器和链接器设置

默认情况下，.NET 项目使用/clr 编译器标志并将链接器配置为面向 x86 硬件。 对于可验证代码，必须使用/clr： safe 标志，并且必须指示链接器生成 MSIL 而不是本机计算机指令。

### <a name="to-change-the-compiler-and-linker-settings"></a>更改编译器和链接器设置

1. 显示项目属性页。 有关详细信息，请参阅 [设置编译器和生成属性](../build/working-with-project-properties.md)。

1. 在 "**配置属性**" 节点下的 "**常规**" 页上，将 "**公共语言运行时支持**" 属性设置为 **安全 MSIL 公共语言运行时支持 (/clr： Safe)**。

1. 在 "**链接器**" 节点下的 "**高级**" 页上，将 " **CLR 映像类型**" 属性设置为 **(/CLRIMAGETYPE： safe) 强制安全 IL 映像**。

## <a name="removing-native-data-types"></a>删除本机数据类型

由于本机数据类型是不可验证的，因此，即使它们实际上并不使用，也必须删除包含本机类型的所有标头文件。

> [!NOTE]
> 下面的过程适用于 Windows 窗体应用程序 ( .NET) 和 ( .NET) 项目的控制台应用程序。

### <a name="to-remove-references-to-native-data-types"></a>删除对本机数据类型的引用

1. 注释掉 Stdafx.h 文件中的所有内容。

## <a name="configuring-an-entry-point"></a>配置入口点

由于可验证应用程序不能使用 (CRT) 的 C 运行时库，因此它们不能依赖于 CRT 来调用主函数作为标准入口点。 这意味着，必须显式提供最初要在链接器中调用的函数的名称。  (在这种情况下，将使用 Main ( # A2，而不是使用 main ( # A4 或 _tmain ( # A6 来指示非 CRT 入口点，但由于必须显式指定入口点，因此此名称是任意的。 ) 

> [!NOTE]
> 以下过程适用于控制台应用程序 ( .NET) 项目。

#### <a name="to-configure-an-entry-point"></a>配置入口点

1. 在项目的主 .cpp 文件中，将 _tmain ( # A1 更改为 Main ( # A3。

1. 显示项目属性页。 有关详细信息，请参阅 [设置编译器和生成属性](../build/working-with-project-properties.md)。

1. 在 "**链接器**" 节点下的 "**高级**" 页上，输入 `Main` 作为 **入口点** 属性值。

## <a name="see-also"></a>请参阅

- [纯代码和可验证代码 (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)
