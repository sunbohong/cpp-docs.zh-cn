---
description: 了解更多：链接器支持延迟加载的 Dll
title: 链接器的延迟加载 DLL 支持
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.openlocfilehash: 9ae1e2c68ed59e742493a9098d98fc35d5f2a7c7
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667274"
---
# <a name="linker-support-for-delay-loaded-dlls"></a>链接器的延迟加载 DLL 支持

MSVC 链接器支持 Dll 的延迟加载。 此功能使您不必使用 Windows SDK 函数 `LoadLibrary` 并 `GetProcAddress` 实现 DLL 延迟加载。

如果没有延迟加载，则在运行时加载 DLL 的唯一方法是使用 `LoadLibrary` 和 `GetProcAddress` ; 当使用和时，操作系统将加载 dll。

使用延迟加载时，隐式链接 DLL 时，链接器会提供一些选项，用于延迟 DLL 加载，直到程序调用该 DLL 中的函数。

应用程序可使用 helper 函数将[ `/DELAYLOAD` (延迟加载导入) ](delayload-delay-load-import.md)链接器选项延迟加载 DLL。  (提供由 Microsoft 提供的默认 helper 函数实现。 ) helper 函数在运行时通过调用 `LoadLibrary` 和来加载 DLL。 `GetProcAddress`

如果出现以下情况，请考虑延迟加载 DLL：

- 程序可能不会调用 DLL 中的函数。

- 在程序执行过程中，可能无法调用 DLL 中的函数。

在 EXE 或 DLL 项目的生成过程中，可以指定 DLL 的延迟加载。 如果 DLL 项目延迟加载一个或多个 Dll，则不应在中调用延迟加载的入口点 `DllMain` 。

以下文章介绍延迟加载 Dll：

- [指定要延迟加载的 Dll](specifying-dlls-to-delay-load.md)

- [显式卸载延迟加载的 DLL](explicitly-unloading-a-delay-loaded-dll.md)

- [加载延迟加载的 DLL 的所有导入](loading-all-imports-for-a-delay-loaded-dll.md)

- [绑定延迟加载的导入](binding-imports.md)

- [错误处理和通知](error-handling-and-notification.md)

- [转储延迟加载的导入](dumping-delay-loaded-imports.md)

- [延迟加载 DLL 的约束](constraints-of-delay-loading-dlls.md)

- [了解 helper 函数](understanding-the-helper-function.md)

- [开发您自己的 helper 函数](developing-your-own-helper-function.md)

## <a name="see-also"></a>请参阅

[在 Visual Studio 中创建 C/C++ DLL](../dlls-in-visual-cpp.md)<br/>
[MSVC 链接器参考](linking.md)
