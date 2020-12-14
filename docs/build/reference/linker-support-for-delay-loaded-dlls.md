---
description: 了解详细信息： Delay-Loaded Dll 的链接器支持
title: 链接器的延迟加载 DLL 支持
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
ms.openlocfilehash: 6bf4527d14c7313874f162f0597114132b1a81cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190960"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>链接器的延迟加载 DLL 支持

MSVC 链接器现在支持 Dll 的延迟加载。 这使你不必使用 Windows SDK 函数 **LoadLibrary** 和 **GETPROCADDRESS** 来实现 DLL 延迟加载。

在 Visual C++ 6.0 之前，在运行时加载 DLL 的唯一方法是使用 **LoadLibrary** 和 **GetProcAddress**;加载 DLL 时，操作系统将加载 DLL。

从 Visual C++ 6.0 开始，隐式链接到 DLL 时，链接器会提供一些选项，用于在程序调用该 DLL 中的函数之前延迟加载 DLL。

应用程序可以使用 [/DELAYLOAD (延迟加载导入) ](delayload-delay-load-import.md) 链接器选项来延迟加载 DLL，并 (Visual C++) 提供的默认实现。 Helper 函数将通过调用 **LoadLibrary** 和 **GetProcAddress** 来在运行时加载 DLL。

如果出现以下情况，应考虑延迟加载 DLL：

- 程序可能不会调用 DLL 中的函数。

- 在程序执行过程中，不会调用 DLL 中的函数。

可以在的生成过程中指定 DLL 的延迟加载。EXE 或。DLL 项目。 的.延迟加载一个或多个 Dll 的 DLL 项目本身不应调用 Dllmain 中延迟加载的入口点。

以下主题介绍延迟加载 Dll：

- [指定要延迟加载的 Dll](specifying-dlls-to-delay-load.md)

- [显式卸载 Delay-Loaded DLL](explicitly-unloading-a-delay-loaded-dll.md)

- [加载 Delay-Loaded DLL 的所有导入](loading-all-imports-for-a-delay-loaded-dll.md)

- [绑定导入](binding-imports.md)

- [错误处理和通知](error-handling-and-notification.md)

- [转储 Delay-Loaded 导入](dumping-delay-loaded-imports.md)

- [延迟加载 Dll 的约束](constraints-of-delay-loading-dlls.md)

- [了解 Helper 函数](understanding-the-helper-function.md)

- [开发您自己的 Helper 函数](developing-your-own-helper-function.md)

## <a name="see-also"></a>请参阅

[在 Visual Studio 中创建 C/C++ DLL](../dlls-in-visual-cpp.md)<br/>
[MSVC 链接器参考](linking.md)
