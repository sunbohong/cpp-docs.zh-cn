---
description: 了解详细信息：调用约定
title: 调用约定
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
ms.openlocfilehash: bb5dab14e9d046b6ccee75a4fb37bd7b105902dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308648"
---
# <a name="calling-conventions"></a>调用约定

Visual C/C++ 编译器提供了用于调用内部函数和外部函数的几个不同的约定。 了解这些不同的方法有助于调试程序以及将你的代码与汇编语言例程链接。

本主题中的各个主题说明了调用约定之间的差异、如何传递参数以及函数如何返回值。 它们也讨论了裸函数调用以及使你能够写入自己的 prolog 和 epilog 代码的高级功能。

有关调用 x64 处理器约定的信息，请参阅 [调用约定](../build/x64-calling-convention.md)。

## <a name="topics-in-this-section"></a>本部分中的主题

- [参数传递和命名约定](../cpp/argument-passing-and-naming-conventions.md) (**`__cdecl`** 、 **`__stdcall`** 、 **`__fastcall`** 和其他) 

- [调用示例：函数原型和调用](../cpp/calling-example-function-prototype-and-call.md)

- [使用裸函数调用编写自定义 prolog/epilog 代码](../cpp/naked-function-calls.md)

- [浮点协处理器和调用约定](../cpp/floating-point-coprocessor-and-calling-conventions.md)

- [已过时调用约定](../cpp/obsolete-calling-conventions.md)

## <a name="see-also"></a>请参阅

[Microsoft 专用的修饰符](../cpp/microsoft-specific-modifiers.md)
