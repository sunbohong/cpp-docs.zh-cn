---
title: C 赋值运算符
description: 标准 C 语言赋值运算符、其语法和含义。
ms.date: 10/30/2020
helpviewer_keywords:
- remainder assignment operator (%=)
- '&= operator'
- bitwise-AND assignment operator
- operators [C], assignment
- operators [C], shift
- ^= operator, assignment operators
- += operator
- '>>= operator'
- '|= operator'
- division assignment operator
- subtraction operator
- right shift operators
- subtraction operator, C assignment operators
- = operator, assignment operators
- '*= operator'
- '>> operator'
- '%= operator'
- assignment operators, C
- = operator
- assignment operators
- assignment conversions
- -= operator
- multiplication assignment operator (*=)
- shift operators, right
- /= operator
- operator >>=, C assignment operators
- <<= operator
ms.assetid: 11688dcb-c941-44e7-a636-3fc98e7dac40
ms.openlocfilehash: 460e18772689de0d28fcfda3295a49b2f8a3c0d7
ms.sourcegitcommit: 4abc6c4c9694f91685cfd77940987e29a51e3143
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "93238507"
---
# <a name="c-assignment-operators"></a>C 赋值运算符

赋值操作将右侧操作数的值分配给左侧操作数命名的存储位置。 因此，赋值操作的左侧操作数必须是一个可修改的左值。 在赋值后，赋值表达式具有左操作数的值，但不是左值。

## <a name="syntax"></a>语法

*`assignment-expression`* :\
&emsp;*`conditional-expression`*\
&emsp;*`unary-expression`* *`assignment-operator`* *`assignment-expression`*

*`assignment-operator`* ：以下之一<br/>
&emsp;**`=`** **`*=`** **`/=`** **`%=`** **`+=`** **`-=`** **`<<=`** **`>>=`** **`&=`** **`^=`** **`|=`**

C 中的赋值运算符可以在单个操作中转换值和赋值。 C 提供了以下赋值运算符：

|运算符|执行的操作|
|--------------|-------------------------|
|**`=`**|简单赋值|
|**`*=`**|乘法赋值|
|**`/=`**|除法赋值|
|**`%=`**|余数赋值|
|**`+=`**|加法赋值|
|**`-=`**|减法赋值|
|**`<<=`**|左移赋值|
|**`>>=`**|右移赋值|
|**`&=`**|按位“与”赋值|
|**`^=`**|按位“异或”赋值|
|**`|=`**|按位“与或”赋值|

在赋值中，右侧值的类型将转换为左侧值的类型，在完成赋值后，该值将存储在左操作数中。 左操作数不得为数组、函数或常量。 [类型转换](../c-language/type-conversions-c.md)中详细介绍了依赖两个类型的特定转换路径。

## <a name="see-also"></a>请参阅

- [赋值运算符](../cpp/assignment-operators.md)
