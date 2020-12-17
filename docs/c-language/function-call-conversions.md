---
description: 详细了解：函数调用转换
title: 函数调用转换
ms.date: 11/04/2016
helpviewer_keywords:
- function calls, converting
- function calls, argument type conversions
- functions [C], argument conversions
ms.assetid: 04ea0f81-509a-4913-8b12-0937a81babcf
ms.openlocfilehash: f37cf2ef6c35cb8e7c856e1ab722a1efda2da61d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195952"
---
# <a name="function-call-conversions"></a>函数调用转换

对函数调用中的自变量执行的转换的类型取决于是否存在具有调用的函数的声明自变量类型的函数原型（前向声明）。

如果函数原型存在并包含声明的参数类型，编译器将执行类型检查（请参阅[函数](../c-language/functions-c.md)）。

如果函数原型不存在，则只对函数调用中的自变量执行常用算术转换。 这些转换独立于调用中的每个自变量执行。 这意味着，`float` 值被转换为 `double`；`char` 或 `short` 值被转换为 `int`；且 `unsigned char` 或 `unsigned short` 被转换为 `unsigned int`。

## <a name="see-also"></a>请参阅

[类型转换](../c-language/type-conversions-c.md)
