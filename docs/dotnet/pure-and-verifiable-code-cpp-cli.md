---
description: '了解更多相关信息：纯代码和可验证代码 (c + +/CLI) '
title: 纯代码和可验证代码 (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], verifiable assemblies
- /clr compiler option [C++], mixed assemblies
- pure MSIL [C++]
- verifiable assemblies [C++]
- verifiably type-safe code [C++]
- /clr compiler option [C++], pure assemblies
- .NET Framework [C++], pure and verifiable code
- assemblies [C++], mixed code
- verifiable assemblies [C++], about verifiable assemblies
- mixed assemblies [C++], about mixed assemblies
- pure MSIL [C++], about pure code
- assemblies [C++], verifiable code
- mixed assemblies [C++]
- assemblies [C++], pure code
ms.assetid: 9050e110-fa11-4356-b56c-665187ff871c
ms.openlocfilehash: 64224f7f462b5e11e522648a5b64ec9d568dc53f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276759"
---
# <a name="pure-and-verifiable-code-ccli"></a>纯代码和可验证代码 (c + +/CLI) 

对于 .NET 编程，Visual Studio 2017 中的 Visual C++ 支持通过使用 [/clr (公共语言运行时编译) ](../build/reference/clr-common-language-runtime-compilation.md) 编译器选项来创建混合程序集。 在 visual Studio 2015 中弃用了 **/clr： pure** 和 **clr： Safe** 选项，visual studio 2017 中不支持此选项。 如果你的代码需要安全或可验证，则我们建议你将其移植到 c #。

## <a name="mixed-clr"></a>混合 (/clr) 

使用 **/clr**) 编译的混合程序集 (包含非托管和托管部分，因此它们可以使用 .net 功能，但仍包含本机代码。 这使得应用程序和组件可以更新为使用 .NET 功能，而无需重写整个项目。 使用以这种方式混合托管代码和本机代码的 Visual C++ 称为 c + + 互操作。 有关详细信息，请参阅 [混合 (本机和托管) 程序集](../dotnet/mixed-native-and-managed-assemblies.md) 以及 [本机和 .Net 互操作性](../dotnet/native-and-dotnet-interoperability.md)。

通过 P/Invoke 从托管程序集到本机 Dll 的调用将进行编译，但在运行时可能失败，具体取决于安全设置。

有一个编码方案会传递编译器，但这会导致无法验证的程序集：使用范围解析运算符通过对象实例调用虚拟函数。  例如：`MyObj -> A::VirtualFunction();`。

## <a name="see-also"></a>请参阅

- [用 c + +/CLI (Visual C++ 的 .NET 编程) ](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
