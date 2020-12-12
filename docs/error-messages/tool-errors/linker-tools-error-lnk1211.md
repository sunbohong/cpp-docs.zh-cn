---
description: 了解详细信息：链接器工具错误 LNK1211
title: 链接器工具错误 LNK1211
ms.date: 12/05/2017
f1_keywords:
- LNK1211
helpviewer_keywords:
- LNK1211
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
ms.openlocfilehash: d3201055643f5874ccc319f04fb6eb2d976bf67f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341615"
---
# <a name="linker-tools-error-lnk1211"></a>链接器工具错误 LNK1211

> 未找到预编译类型信息;未链接或覆盖 "*filename*"

LINK 命令中未指定使用 [/yc](../../build/reference/yc-create-precompiled-header-file.md)编译的 *文件名* 对象文件，或该文件已被覆盖。

如果要创建使用预编译标头的调试库，并且指定 **/yc** 和 [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)，Visual C++ 会生成包含调试信息的预编译对象文件。 仅在将预编译对象文件存储到库中、使用库生成可执行映像，并且所引用的对象文件没有对预编译对象文件定义的任何函数的传递引用的情况下才会发生此错误。

可通过两种方法解决此问题：

- 指定 [/yd](../../build/reference/yd-place-debug-information-in-object-file.md) 编译器选项，将预编译标头中的调试信息添加到每个对象模块。 此方法不太理想，因为它通常会生成大型对象模块，从而增加链接应用程序所需的时间。

- 当创建不包含任何函数定义的预编译头文件时，请指定 [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) 并传递任意字符串的名称。 这会指示编译器在预编译对象文件中创建一个符号，并在每个使用与预编译对象文件关联的预编译头文件的对象文件中发出对该符号的引用。

使用 **/yc** 和 **/Yl** 编译模块时，编译器会创建类似于的符号 `__@@_PchSym_@00@...@symbol_name` ，其中省略号 ( ... ) 表示编译器生成的字符串，并将其存储在对象模块中。 用此预编译头编译的任何源文件都引用指定的符号，这会导致链接器将对象模块及其调试信息包含在库中。
