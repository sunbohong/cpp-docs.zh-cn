---
title: continue 语句 (C)
ms.date: 11/04/2016
f1_keywords:
- continue
helpviewer_keywords:
- loop structures, continue keyword
- continue keyword [C]
ms.assetid: 969f293a-45fe-48a7-b4c6-287ba27a631d
ms.openlocfilehash: 27d1d0aa0e49c5c46e4ea4e010635ca0057c3f85
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684828"
---
# <a name="continue-statement-c"></a>continue 语句 (C)

`continue` 语句将控制权传递给出现它的最近的封闭 `do`、`for` 或 `while` 语句的下一个迭代，并绕过 `do`、`for` 或 `while` 语句主体中的任何剩余语句。

## <a name="syntax"></a>语法

*jump-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**continue ;**

`do`、`for` 或 `while` 语句的下一个迭代是按如下方式确定的：

- 在 `do` 或 `while` 语句中，下一个迭代会先重新计算 `do` 或 `while` 语句的表达式。

- `for` 语句中的 `continue` 语句会导致计算 `for` 语句的循环表达式。 然后，编译器会重新计算条件表达式并根据结果终止或迭代语句主体。 若要详细了解 `for` 语句及其非终止符，请参阅 [for 语句](../c-language/for-statement-c.md)。

下面的示例展示了 `continue` 语句：

```C
while ( i-- > 0 )
{
    x = f( i );
    if ( x == 1 )
        continue;
    y += x * x;
}
```

在此示例中，当 `i` 大于 0 时，将执行语句主体。 首先将 `f(i)` 赋给 `x`；然后，如果 `x` 等于 1，则执行 `continue` 语句。 主体中的语句的其余部分将被忽略，并且执行将通过计算循环的测试来基于循环恢复。

## <a name="see-also"></a>请参阅

[continue 语句](../cpp/continue-statement-cpp.md)
