---
description: 详细了解：C 语句概述
title: C 语句概述
ms.date: 11/04/2016
helpviewer_keywords:
- semicolon, in C statements
- statements, C
- semicolon
- statements, about statements
- Visual C, statements
ms.assetid: 0d49837a-5399-4881-b60c-af5f4e9720de
ms.openlocfilehash: d2d6e7161f63e8508cb7e94d28b7bbafe44146e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243167"
---
# <a name="overview-of-c-statements"></a>C 语句概述

C 语句由标记、表达式和其他语句组成。 构成另一个语句的组成部分的语句称为封闭语句的“体”。 本节中将讨论以下语法给定的每个语句类型。

## <a name="syntax"></a>语法

*statement*: [labeled-statement](../c-language/goto-and-labeled-statements-c.md)

[compound-statement](../c-language/compound-statement-c.md)

[expression-statement](../c-language/expression-statement-c.md)

[selection-statement](../c-language/if-statement-c.md)

[iteration-statement](../c-language/do-while-statement-c.md)

[jump-statement](../c-language/break-statement-c.md)

[try-except-statement](../c-language/try-except-statement-c.md) /* Microsoft-specific \*/

[try-finally-statement](../c-language/try-finally-statement-c.md) /\* Microsoft-specific \*/

通常，语句体为“复合语句”。 复合语句由可包含关键字的其他语句组成。 复合语句由大括号 ({ }  ) 分隔。 所有其他 C 语句以分号 (;  ) 结尾。 分号是语句结束符。

表达式语句包含可包含[表达式和赋值](../c-language/expressions-and-assignments.md)中介绍的算术或逻辑运算符的 C 表达式。 null 语句是空语句。

所有 C 语句都可以以由名称和冒号组成的标识标签开头。 由于只有 `goto` 语句才能识别语句标签，因此将用 `goto` 介绍语句标签。 有关详细信息，请参阅 [goto 和标记语句](../c-language/goto-and-labeled-statements-c.md)。

## <a name="see-also"></a>请参阅

[语句](../c-language/statements-c.md)
