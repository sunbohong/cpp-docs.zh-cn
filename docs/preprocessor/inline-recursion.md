---
description: 了解详细信息： inline_recursion 杂注
title: inline_recursion 杂注
ms.date: 08/29/2019
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
ms.openlocfilehash: 1688eb724a9a76ce3f173c7f9eac7d52032fbe13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236368"
---
# <a name="inline_recursion-pragma"></a>inline_recursion 杂注

控制直接或相互递归函数调用的内联扩展。

## <a name="syntax"></a>语法

> **#pragma inline_recursion (** [{ **on**  |  **off** }] **)**

## <a name="remarks"></a>备注

使用此杂注控制标记为 [inline](../cpp/inline-functions-cpp.md) 的函数以及编译器在选项下自动扩展的 [__inline](../cpp/inline-functions-cpp.md) 或函数 `/Ob2` 。 使用此杂注要求 [/Ob](../build/reference/ob-inline-function-expansion.md) 编译器选项设置为1或2。 **Inline_recursion** 的默认状态为 off。 此杂注在出现杂注后的第一个函数调用处生效，且不会影响函数的定义。

**Inline_recursion** 杂注控制如何扩展递归函数。 如果 **inline_recursion** 为 off，并且内联函数直接或间接调用自身，则只展开一次此函数。 如果 **inline_recursion** 为 on，则函数将展开多次，直到它达到使用 [inline_depth](../preprocessor/inline-depth.md) 杂注设置的值、由杂注定义的递归函数的默认值 `inline_depth` 或容量限制。

## <a name="see-also"></a>请参阅

[Pragma 指令和 __pragma 关键字](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[inline_depth](../preprocessor/inline-depth.md)\
[/Ob (内联函数扩展) ](../build/reference/ob-inline-function-expansion.md)
