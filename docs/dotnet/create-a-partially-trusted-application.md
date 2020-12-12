---
description: 了解详细信息：如何：通过移除 CRT 库 DLL 上的依赖项来创建部分受信任的应用程序
title: '如何：在 c + +/CLI (创建部分受信任的应用程序) '
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- partially trusted applications [C++]
- mixed assemblies [C++], partially trusted applications
- msvcm90[d].dll
- interoperability [C++], partially trusted applications
- interop [C++], partially trusted applications
- /clr compiler option [C++], partially trusted applications
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
ms.openlocfilehash: 937262595df4415d5620b60d9ccd8c17a6c44abf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124275"
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>如何：通过移除 CRT 库 DLL 上的依赖项来创建部分受信任的应用程序

本主题讨论如何通过删除 msvcm90.dll 上的依赖项来创建部分受信任的公共语言运行时应用程序 Visual C++。

使用 **/clr** 生成的 Visual C++ 应用程序将依赖于 msvcm90.dll，这是 C 运行时库的一部分。 如果希望应用程序在部分信任环境中使用，则 CLR 会在 DLL 上强制实施某些代码访问安全规则。 因此，需要删除此依赖项，因为不能对其强制实施 msvcm90.dll 包含本机代码和代码访问安全策略。

如果你的应用程序不使用 C 运行时库的任何功能，并且你想要从代码中删除此库的依赖项，则必须使用 **/NODEFAULTLIB： msvcmrt.lib** 链接器选项并与 ptrustm 或 ptrustmd 链接。 这些库包含用于初始化和取消初始化应用程序的对象文件、初始化代码使用的异常类以及托管的异常处理代码。 在其中一个库中链接会删除 msvcm90.dll 上的任何依赖项。

> [!NOTE]
> 对于使用 ptrust 库的应用程序，程序集取消初始化的顺序可能会有所不同。 对于普通应用程序，通常以加载程序集的相反顺序卸载程序集，但不保证这样做。 对于部分信任的应用程序，通常以加载程序集的相同顺序卸载程序集。 这也是不能保证的。

### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>创建部分受信任的混合 (/clr) 应用程序

1. 若要删除 msvcm90.dll 上的依赖关系，必须使用 **/NODEFAULTLIB： msvcmrt.lib** 链接器选项指定链接器不包含此库。 有关如何使用 Visual Studio 开发环境或以编程方式执行此操作的信息，请参阅 [/NODEFAULTLIB (Ignore 盘库) ](../build/reference/nodefaultlib-ignore-libraries.md)。

1. 将其中一个 ptrustm 库添加到链接器输入依赖项。 如果要在发布模式下构建应用程序，请使用 ptrustm。 对于调试模式，请使用 ptrustmd。 有关如何使用 Visual Studio 开发环境或以编程方式执行此操作的信息，请参阅 [。用作链接器输入的 .lib 文件](../build/reference/dot-lib-files-as-linker-input.md)。

## <a name="see-also"></a>请参阅

[混合 (本机和托管) 程序集](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
[混合程序集的初始化](../dotnet/initialization-of-mixed-assemblies.md)<br/>
[混合程序集的库支持](../dotnet/library-support-for-mixed-assemblies.md)<br/>
[/link (将选项传递给链接器) ](../build/reference/link-pass-options-to-linker.md)
