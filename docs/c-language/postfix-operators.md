---
description: 详细了解：后缀运算符
title: 后缀运算符
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C], postfix
- postfix operators
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
ms.openlocfilehash: be8e7354d512174a4ab11ffcdcb82f9418baa894
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195861"
---
# <a name="postfix-operators"></a>后缀运算符

后缀运算符在表达式计算中具有最高优先级（最紧密的绑定）。

## <a name="syntax"></a>语法

*postfix-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*primary-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **[**  *expression*  **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **(**  *argument-expression-list*<sub>opt</sub> **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **.**  *identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **->**  *identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **--**

具有此优先级别的运算符为数组下标、函数调用、结构和联合成员以及后缀递增和递减运算符。

## <a name="see-also"></a>请参阅

[C 运算符](../c-language/c-operators.md)
