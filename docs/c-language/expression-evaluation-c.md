---
description: 详细了解：表达式计算 (C)
title: 表达式计算 (C)
ms.date: 11/04/2016
helpviewer_keywords:
- expression evaluation
- expressions [C++], evaluating
ms.assetid: 9493f8cc-64a2-4284-9aaf-26eec11c4f40
ms.openlocfilehash: 740cb7a7bc14b598c45b3c8f45e719dcb85372e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196446"
---
# <a name="expression-evaluation-c"></a>表达式计算 (C)

涉及赋值、一元递增、一元递减或调用函数的表达式可能具有其计算附带的结果（副作用）。 当达到“序列点”时，确保对序列点后面的任何内容执行计算之前已计算序列点前面的所有内容（包括任何副作用）。

“副作用”是由表达式的计算引起的更改。 只要表达式计算更改变量的值，就会出现副作用。 所有赋值运算都具有副作用。 如果函数调用通过直接赋值或使用指针进行间接赋值来更改外部可见项的值，则函数调用还会产生副作用。

## <a name="see-also"></a>请参阅

[操作数和表达式](../c-language/operands-and-expressions.md)
