---
description: 详细了解：while 语句 (C)
title: While 语句 (C)
ms.date: 11/04/2016
f1_keywords:
- while
helpviewer_keywords:
- while keyword [C]
- while keyword [C], syntax
ms.assetid: d0c970b8-12a9-4827-afb2-a051111834b7
ms.openlocfilehash: 3461372de48980a0591f890fdd366c9373aea78f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221847"
---
# <a name="while-statement-c"></a>While 语句 (C)

利用 `while` 语句，可以重复执行语句，直到指定的 expression 变成 false。

## <a name="syntax"></a>语法

*iteration-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**while (**  *expression*  **)**  *statement*

expression  必须具有算法或指针类型。 执行过程如下所示：

1. 计算 expression  。

1. 如果 expression 最初为 false，则 `while` 语句的主体永远不会执行，并且控制权从 `while` 语句传递给程序中的下一个语句。

   如果 expression  为 true（非零），则执行语句体，并且此过程从第 1 步开始重复。

当语句主体中的 `break`、`goto` 或 `return` 执行时，`while` 语句也可以终止。 使用 `continue` 语句可以在不退出 `while` 循环的情况下终止迭代。 `continue` 语句将控制权传递给 `while` 语句的下一个迭代。

下面的示例展示了 `while` 语句：

```C
while ( i >= 0 )
{
    string1[i] = string2[i];
    i--;
}
```

此示例将 `string2` 中的字符复制到 `string1`。 如果 `i` 大于或等于 0，则 `string2[i]` 将赋给 `string1[i]`，并且 `i` 将递减。 当 `i` 达到或小于 0 时，`while` 语句的执行终止。

## <a name="see-also"></a>请参阅

[While 语句 (C++)](../cpp/while-statement-cpp.md)
