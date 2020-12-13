---
description: '了解详细信息： continue 语句 (c + +) '
title: continue 语句 (C++)
ms.date: 11/04/2016
f1_keywords:
- continue_cpp
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
ms.openlocfilehash: 6899e5cd249ab5a7a3b786e4b82c9890c08a7183
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344635"
---
# <a name="continue-statement-c"></a>continue 语句 (C++)

强制将控制传输到最小封闭 [do](../cpp/do-while-statement-cpp.md)、 [for](../cpp/for-statement-cpp.md)或 [while](../cpp/while-statement-cpp.md) 循环的控制表达式。

## <a name="syntax"></a>语法

```
continue;
```

## <a name="remarks"></a>备注

将不会执行当前迭代中的所有剩余语句。 确定循环的下一次迭代，如下所示：

- 在 **`do`** 或 **`while`** 循环中，下一个迭代首先重新计算或语句的控制表达式 **`do`** **`while`** 。

- 在 **`for`** 循环 (使用语法 `for( <init-expr> ; <cond-expr> ; <loop-expr> )`) ，将 `<loop-expr>` 执行子句。 然后，重新计算 `<cond-expr>` 子句，并根据结果确定该循环结束还是进行另一个迭代。

下面的示例演示如何 **`continue`** 使用语句跳过代码段和开始循环的下一次迭代。

## <a name="example"></a>示例

```cpp
// continue_statement.cpp
#include <stdio.h>
int main()
{
    int i = 0;
    do
    {
        i++;
        printf_s("before the continue\n");
        continue;
        printf("after the continue, should never print\n");
     } while (i < 3);

     printf_s("after the do loop\n");
}
```

```Output
before the continue
before the continue
before the continue
after the do loop
```

## <a name="see-also"></a>请参阅

[跳转语句](../cpp/jump-statements-cpp.md)<br/>
[关键字](../cpp/keywords-cpp.md)
