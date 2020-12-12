---
description: 了解详细信息：了解 Helper 函数
title: 了解 Helper 函数
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
ms.openlocfilehash: d47e392d78d6cf872af28b992885c57d34bddf0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247093"
---
# <a name="understanding-the-helper-function"></a>了解 Helper 函数

链接器支持的延迟加载的 helper 函数是实际在运行时加载 DLL 的内容。 您可以通过编写自己的函数并将其链接到您的程序，而不是使用 Delayimp.lib 中提供的帮助程序函数，来修改 helper 函数以自定义其行为。 一个 helper 函数提供所有延迟加载的 Dll。

如果要基于 DLL 或导入的名称进行特定处理，则可以提供自己的 helper 函数版本。

Helper 函数执行以下操作：

- 检查库的存储句柄，查看其是否已加载

- 调用 **LoadLibrary** 尝试加载 DLL

- 调用 **GetProcAddress** 以尝试获取过程的地址

- 返回到延迟导入加载 thunk 以调用现在加载的入口点

在以下每个操作后，helper 函数可以回调到程序中的通知挂钩：

- Helper 函数启动时

- 紧靠在 helper 函数中调用 **LoadLibrary** 之前

- 紧靠在 helper 函数中调用 **GetProcAddress** 之前

- 如果 helper 函数中对 **LoadLibrary** 的调用失败

- 如果 helper 函数中的 **GetProcAddress** 调用失败

- 完成处理 helper 函数后

其中的每个挂钩点都可以返回一个值，该值将以某种方式更改 helper 例程的正常处理，但返回延迟导入负载 thunk 除外。

可以在 vc\include) 中的 Delayhlp 和 Delayimp.lib (中找到默认帮助程序代码，并将其编译为 vc\lib) 中的 Delayimp.lib (。 你需要在编译中包含此库，除非你编写自己的 helper 函数。

以下主题介绍 helper 函数：

- [DLL 中的更改延迟加载 Helper 函数，因为 Visual C++ 6。0](changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)

- [调用约定、参数和返回类型](calling-conventions-parameters-and-return-type.md)

- [结构和常量定义](structure-and-constant-definitions.md)

- [计算必需的值](calculating-necessary-values.md)

- [卸载 Delay-Loaded DLL](explicitly-unloading-a-delay-loaded-dll.md)

## <a name="see-also"></a>请参阅

[Delay-Loaded Dll 的链接器支持](linker-support-for-delay-loaded-dlls.md)
