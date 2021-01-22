---
description: 了解有关延迟加载 helper 函数的详细信息
title: 了解延迟加载 helper 函数
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.openlocfilehash: a4b25a51af25458f5add5ed7eb3fd58f759dae7b
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667258"
---
# <a name="understand-the-delay-load-helper-function"></a>了解延迟加载 helper 函数

链接器支持的延迟加载的 helper 函数是实际在运行时加载 DLL 的内容。 您可以修改 helper 函数以自定义其行为：而不是使用中提供的 helper 函数，而是 *`delayimp.lib`* 编写您自己的函数并将其链接到您的程序。 一个 helper 函数提供所有延迟加载的 Dll。

如果要基于 DLL 或导入的名称进行特定处理，则可以提供自己的 helper 函数版本。

Helper 函数会执行以下操作：

- 检查库的存储句柄，查看其是否已加载

- 调用 `LoadLibrary` 以尝试加载 DLL

- 调用 `GetProcAddress` 以尝试获取过程的地址

- 返回到延迟导入加载 thunk 以调用现在加载的入口点

在以下每个操作后，helper 函数可以回调到程序中的通知挂钩：

- Helper 函数启动时

- 紧靠 `LoadLibrary` 在 helper 函数中调用之前

- 紧靠 `GetProcAddress` 在 helper 函数中调用之前

- 如果 `LoadLibrary` helper 函数中的调用失败

- 如果 `GetProcAddress` helper 函数中的调用失败

- 完成处理 helper 函数后

其中每个挂钩点都可以返回一个值，该值将以某种方式更改 helper 例程的正常处理，但返回延迟导入负载 thunk 除外。

默认帮助程序代码可在 *`Delayhlp.cpp`* *`Delayimp.h`* vc 目录) 中找到并 (， *`include`* 并在 *`Delayimp.lib`* vc 目录)  (中进行编译 *`lib`* 。 你需要在编译中包含此库，除非你编写自己的 helper 函数。

以下文章介绍了 helper 函数：

- [自 Visual C++ 6.0 以来 DLL 延迟加载 Helper 函数所做的更改](changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)

- [调用约定、参数和返回类型](calling-conventions-parameters-and-return-type.md)

- [结构和常量定义](structure-and-constant-definitions.md)

- [计算必需值](calculating-necessary-values.md)

- [显式卸载延迟加载的 DLL](explicitly-unloading-a-delay-loaded-dll.md)

## <a name="see-also"></a>另请参阅

[链接器的延迟加载 DLL 支持](linker-support-for-delay-loaded-dlls.md)
