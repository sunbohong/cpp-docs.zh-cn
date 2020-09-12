---
title: C/C++ 预处理器参考
description: Visual Studio 中 Microsoft C/c + + 编译器预处理器参考。
ms.date: 09/10/2020
helpviewer_keywords:
- preprocessor
- preprocessor, reference overview
ms.assetid: e4a52843-7016-4f6d-8b40-cb1ace18f805
ms.openlocfilehash: e53f7270a71e5e7c3f456be7d55d49eaf352aecb
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040738"
---
# <a name="cc-preprocessor-reference"></a>C/C++ 预处理器参考

*C/c + + 预处理器参考*说明了在 Microsoft c/c + + 中实现的预处理器。 在将 C 和 C++ 文件传递到编译器之前，预处理器将对这些文件执行预先操作。 可以使用预处理器有条件地编译代码、插入文件、指定编译时错误消息以及将计算机特定规则应用于代码节。

在 Visual Studio 2019 中， [/experimental：预处理器](../build/reference/experimental-preprocessor.md) 编译器选项启用新的预处理器实现。 新的实现仍在进行中，因此被视为实验性。 它最终与 C99、C11 和 c + + 20 一致。 有关详细信息，请参阅 [MSVC new 预处理器概述](preprocessor-experimental-overview.md)。

## <a name="in-this-section"></a>在本节中

[程序](preprocessor.md)\
概述传统和新的符合预处理器。

[预处理器指令](../preprocessor/preprocessor-directives.md)\
介绍通常用于使源程序易于在不同的执行环境中更改和编译的指令。

[预处理器运算符](../preprocessor/preprocessor-operators.md)\
讨论在 `#define` 指令的上下文中使用的四个预处理器特定运算符。

[预定义的宏](../preprocessor/predefined-macros.md)\
讨论 C 和 c + + 标准指定的预定义宏和 Microsoft c + +。

[杂注](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
讨论杂注，杂注提供了一种方法来让每个编译器提供计算机和操作系统特定的功能，同时保持与 C 和 C++ 语言的整体兼容性。

## <a name="related-sections"></a>相关章节

[C + + 语言参考](../cpp/cpp-language-reference.md)\
提供有关 Microsoft 的 C++ 语言实现的参考材料。

[C 语言参考](../c-language/c-language-reference.md)\
提供有关 Microsoft 的 C 语言实现的参考材料。

[C/c + + 生成参考](../build/reference/c-cpp-building-reference.md)\
提供指向讨论编译器和链接器选项的主题的链接。

[Visual Studio 项目-c + +](../build/creating-and-managing-visual-cpp-projects.md)\
描述 Visual Studio 中使您能够指定目录（项目系统将在其中进行搜索以找到 C++ 项目的文件）的用户界面。
