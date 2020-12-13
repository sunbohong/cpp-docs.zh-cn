---
description: 了解详细信息：自 Visual C++ 6.0 起，DLL 延迟加载 Helper 函数的更改
title: 自 Visual C++ 6.0 以来 DLL 延迟加载 Helper 函数所做的更改
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.assetid: 99f0be69-105d-49ba-8dd5-3be7939c0c72
ms.openlocfilehash: 0141467aab0b804cf82d21c15510d8f9941853a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182484"
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>自 Visual C++ 6.0 以来 DLL 延迟加载 Helper 函数所做的更改

如果你的计算机上有多个版本的 Visual C++ 或你定义了自己的 helper 函数，则可能会影响对 DLL 延迟加载 helper 函数所做的更改。 例如：

- **__delayLoadHelper** 现在 **__delayLoadHelper2**

- **__pfnDliNotifyHook** 现在 **__pfnDliNotifyHook2**

- **__pfnDliFailureHook** 现在 **__pfnDliFailureHook2**

- **__FUnloadDelayLoadedDLL** 现在 **__FUnloadDelayLoadedDLL2**

> [!NOTE]
> 如果你使用的是默认 helper 函数，则这些更改不会影响你。 没有关于如何调用链接器的更改。

## <a name="multiple-versions-of-visual-c"></a>Visual C++ 的多个版本

如果你的计算机上有多个版本的 Visual C++，请确保链接器与 delayimp.lib 匹配。 如果存在不匹配的情况，您将收到 `___delayLoadHelper2@8` `___delayLoadHelper@8` 作为无法解析的外部符号报告或的链接器错误。 前者表示新的链接器使用旧的 delayimp.lib，后者表示具有新 delayimp.lib 的旧链接器。

如果获取了无法解析的链接器错误，请在要包含 helper 函数的 delayimp.lib 上运行 [dumpbin/linkermember](linkermember.md)：1，以查看改为定义的 helper 函数。 Helper 函数也可以在对象文件中定义;运行 [dumpbin/symbols](symbols.md) ，并查找 `delayLoadHelper(2)` 。

如果知道有 Visual C++ 6.0 链接器，请执行以下操作：

- 在延迟加载帮助器的 .lib 或 .obj 文件上运行 dumpbin，以确定它是否定义 **__delayLoadHelper2**。 如果不是，则链接将失败。

- 在延迟加载助手的 .lib 或 .obj 文件中定义 **__delayLoadHelper** 。

## <a name="user-defined-helper-function"></a>User-Defined Helper 函数

如果定义了自己的 helper 函数并使用当前版本的 Visual C++，请执行以下操作：

- 将 helper 函数重命名为 **__delayLoadHelper2**。

- 由于延迟描述符中的指针 (在 delayimp.lib 中的 ImgDelayDescr) 已从 (VAs) 的绝对地址更改为相对地址 (Rva) ，在32和64程序中按预期方式工作，因此需要将它们转换回指针。 引入了一个新函数： PFromRva，在 delayhlp 中找到。 可以对描述符中的每个字段使用此函数，以将其转换回32或64位指针。 默认延迟加载 helper 函数继续作为示例使用的一个好模板。

## <a name="load-all-imports-for-a-delay-loaded-dll"></a>加载 Delay-Loaded DLL 的所有导入

链接器可以从您指定为延迟加载的 DLL 加载所有导入。 有关详细信息，请参阅 [加载 Delay-Loaded DLL 的所有导入](loading-all-imports-for-a-delay-loaded-dll.md) 。

## <a name="see-also"></a>请参阅

[了解 Helper 函数](understanding-the-helper-function.md)
