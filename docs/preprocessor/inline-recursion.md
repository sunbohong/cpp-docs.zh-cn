---
description: 详细了解 pragma Microsoft c/c + + 中的 inline_recursion 指令
title: inline_recursion pragma
ms.date: 01/22/2021
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
helpviewer_keywords:
- pragma, inline_recursion
- inline_recursion pragma
no-loc:
- pragma
ms.openlocfilehash: b4e377d4c97c46a20e44a2c41f872a8762cdea4d
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713553"
---
# <a name="inline_recursion-no-locpragma"></a>`inline_recursion` pragma

控制直接或相互递归函数调用的内联扩展。

## <a name="syntax"></a>语法

> **`#pragma inline_recursion(`** [ { **`on`** | **`off`** } ] **`)`**

## <a name="remarks"></a>注解

使用此 pragma 选项可控制标记为 [`inline`](../cpp/inline-functions-cpp.md) 和的函数 [`__inline`](../cpp/inline-functions-cpp.md) 或编译器在选项下自动扩展的函数 **`/Ob2`** 。 使用此 pragma [`/Ob`](../build/reference/ob-inline-function-expansion.md) 选项要求编译器选项设置为1或2。 的默认状态为 **`inline_recursion`** off。 这会在 pragma 出现后的第一个函数调用中生效 pragma ，且不会影响函数的定义。

**`inline_recursion`** pragma 控制如何扩展递归函数。 如果 **`inline_recursion`** 处于关闭状态，并且内联函数直接或间接调用自身，则只展开一次函数。 如果 **`inline_recursion`** 为 on，则函数将展开多次，直到它到达使用设置的值 [`inline_depth`](../preprocessor/inline-depth.md) pragma 、由定义的递归函数的默认值 `inline_depth` pragma 或容量限制。

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)\
[`inline_depth`](../preprocessor/inline-depth.md)\
[`/Ob` (内联函数展开) ](../build/reference/ob-inline-function-expansion.md)
