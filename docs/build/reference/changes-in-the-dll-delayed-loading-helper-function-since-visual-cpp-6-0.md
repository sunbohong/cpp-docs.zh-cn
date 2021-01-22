---
description: 了解详细信息：自 Visual C++ 6.0 起，DLL 延迟加载 helper 函数的更改
title: 自 Visual C++ 6.0 以来 DLL 延迟加载 Helper 函数所做的更改
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, what's changed
- PFromRva method
- __delayLoadHelper2 function
- helper functions, what's changed
ms.openlocfilehash: a83d5e2895863efde396c48d68316e32aa42a2a1
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666961"
---
# <a name="changes-in-the-dll-delayed-loading-helper-function-since-visual-c-60"></a>自 Visual C++ 6.0 以来 DLL 延迟加载 Helper 函数所做的更改

如果你的计算机上有多个版本的 Visual C++，或如果定义了自己的 helper 函数，对 DLL 延迟加载 helper 函数所做的更改可能会影响你。 例如：

- **`__delayLoadHelper`** 现在为 `__delayLoadHelper2`

- `__pfnDliNotifyHook` 现为 `__pfnDliNotifyHook2`

- `__pfnDliFailureHook` 现为 `__pfnDliFailureHook2`

- `__FUnloadDelayLoadedDLL` 现为 `__FUnloadDelayLoadedDLL2`

> [!NOTE]
> 如果你使用的是默认 helper 函数，则这些更改不会影响你。 没有关于如何调用链接器的更改。

## <a name="multiple-versions-of-visual-c"></a>Visual C++ 的多个版本

如果你的计算机上有多个版本的 Visual C++，请确保链接器匹配 *`delayimp.lib`* 。 如果存在不匹配的情况，您将收到 `___delayLoadHelper2@8` `___delayLoadHelper@8` 作为无法解析的外部符号报告或的链接器错误。 前者表示新的链接器具有旧的 *`delayimp.lib`* ，后者表示具有新的旧链接器 *`delayimp.lib`* 。

如果您收到了无法解析的链接器错误，请 [`dumpbin /linkermember:1`](linkermember.md) 在 *`delayimp.lib`* 您希望包含 helper 函数的中运行，以查看所定义的 helper 函数。 Helper 函数也可以在对象文件中定义;运行 [`dumpbin /symbols`](symbols.md) 和查找 `delayLoadHelper` 或 `delayLoadHelper2` 。

如果知道有 Visual C++ 6.0 链接器，请执行以下操作：

- **`dumpbin`** 在延迟加载帮助程序 *`.lib`* 或文件上运行 *`.obj`* ，以确定它是否定义 `__delayLoadHelper2` 。 如果不是，则链接将失败。

- `__delayLoadHelper`在延迟加载帮助程序的 *`.lib`* 或文件中定义 *`.obj`* 。

## <a name="user-defined-helper-function"></a>用户定义 helper 函数

如果定义了自己的 helper 函数并使用当前版本的 Visual C++，请执行以下步骤：

- 将 helper 函数重命名为 `__delayLoadHelper2` 。

- 由于在) 中 (延迟描述符中的指针已 `ImgDelayDescr` *`delayimp.h`* 从 (VAs) 的绝对地址更改为相对地址 (rva) 在32位和64位程序中按预期方式工作，因此需要将这些 rva 转换回指针。 引入了一个新函数： `PFromRva` ，在中找到了 *`delayhlp.cpp`* 。 可以对描述符中的每个字段使用此函数，以将其转换回32位或64位指针。 默认延迟加载 helper 函数继续作为示例使用的一个好模板。

## <a name="load-all-imports-for-a-delay-loaded-dll"></a>加载延迟加载的 DLL 的所有导入

链接器可以从您指定为延迟加载的 DLL 加载所有导入。 有关详细信息，请参阅 [加载延迟加载的 DLL 的所有导入](loading-all-imports-for-a-delay-loaded-dll.md)。

## <a name="see-also"></a>另请参阅

[了解 Helper 函数](understanding-the-helper-function.md)
