---
description: 详细了解：函数体
title: 函数体
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
ms.openlocfilehash: 098a759a8fd4fd9ab69e487ab84f7ed7d0d2c25c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195978"
---
# <a name="function-body"></a>函数体

函数体  是包含指定函数行为的语句的复合语句。

## <a name="syntax"></a>语法

function-definition  ：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers*<sub>opt</sub> *attribute-seq*<sub>opt</sub> *declarator* *declaration-list*<sub>opt</sub> *compound-statement*

/\* *attribute-seq* is Microsoft-specific \*/

compound-statement  ：/\* 函数体 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **{** *declaration-list*<sub>opt</sub> *statement-list*<sub>opt</sub> **}**

除非另有说明，否则在函数主体中声明的变量（称为“局部变量”）包含 `auto` 存储类。 调用函数时，将为局部变量创建存储并执行本地初始化。 执行控制权传递给 compound-statement 中的第一个语句，并继续传递，直到执行了 `return` 语句或到达函数主体的末尾。 控制权随后返回到调用功能的点。

如果函数要返回值，则必须执行包含表达式的 `return` 语句。 如果没有执行 `return` 语句或 `return` 语句不包含表达式，则函数的返回值是未定义的。

## <a name="see-also"></a>请参阅

[C 函数定义](../c-language/c-function-definitions.md)
