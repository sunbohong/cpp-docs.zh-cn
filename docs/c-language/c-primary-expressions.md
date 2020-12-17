---
title: C 主要表达式
description: 解释什么是 C 主要表达式
ms.date: 12/08/2020
helpviewer_keywords:
- primary expressions
ms.openlocfilehash: 41f011cc56f4c4fdf58c6a5fd2e3178267995854
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300198"
---
# <a name="c-primary-expressions"></a>C 主要表达式

主表达式是更复杂的表达式的构造块。 它们可以是常数、标识符、[泛型选择](generic_selection.md)，或者是括号中的表达式。

## <a name="syntax"></a>语法

*`primary-expression`*:\
&nbsp;&nbsp;&nbsp;&nbsp;*`identifier`*\
&nbsp;&nbsp;&nbsp;&nbsp;*`constant`*\
&nbsp;&nbsp;&nbsp;&nbsp;*`string-literal`*\
&nbsp;&nbsp;&nbsp;&nbsp;**(** *`expression`* **)**\
&nbsp;&nbsp;&nbsp;&nbsp;*`generic-selection`*

*expression*:\
&nbsp;&nbsp;&nbsp;&nbsp;*`assignment-expression`*\
&nbsp;&nbsp;&nbsp;&nbsp;*`expression`***,** *`assignment-expression`*

## <a name="see-also"></a>另请参阅

[泛型表达式](generic_selection.md)
[操作数和表达式](../c-language/operands-and-expressions.md)
