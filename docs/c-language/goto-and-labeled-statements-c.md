---
description: 了解详细信息：goto 和标记语句 (C)
title: goto 和标记语句 (C)
ms.date: 11/04/2016
f1_keywords:
- goto
helpviewer_keywords:
- labeled statement
- statements, labeled
- goto keyword [C]
ms.assetid: 3d0473dc-4b18-4fcc-9616-31a38499d7d7
ms.openlocfilehash: 1372cd0699944449ccd44a76dd1d90206bfab68a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137639"
---
# <a name="goto-and-labeled-statements-c"></a>goto 和标记语句 (C)

`goto` 语句将控制权转移给标签。 给定标签必须位于同一函数中，并且只可以出现在同一函数中的一个语句前面。

## <a name="syntax"></a>语法

*statement*：<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*labeled-statement*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*jump-statement*

*jump-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;`goto`  identifier  ;

*labeled-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*identifier*  **:**  *statement*

语句标签只对 `goto` 语句有意义；在其他任何上下文中，执行带标签的语句时不考虑标签。

jump-statement 必须位于同一函数中，并且只能出现在同一函数中的一个语句前面。 `goto` 后面的 identifier 名称集有自己的命名空间，因此名称不会干扰其他标识符。 不能重新声明标签。 有关详细信息，请参阅[命名空间](../c-language/name-spaces.md)。

尽可能优先使用 `break`、`continue` 和 `return` 语句，而不是 `goto`，这是很好的编程风格。 由于 `break` 语句只从循环的一个级别退出，因此从深度嵌套的循环中退出循环可能需要使用 `goto`。

下面的示例展示了 `goto` 语句：

```c
// goto.c
#include <stdio.h>

int main()
{
    int i, j;

    for ( i = 0; i < 10; i++ )
    {
        printf_s( "Outer loop executing. i = %d\n", i );
        for ( j = 0; j < 3; j++ )
        {
            printf_s( " Inner loop executing. j = %d\n", j );
            if ( i == 5 )
                goto stop;
        }
    }

    /* This message does not print: */
    printf_s( "Loop exited. i = %d\n", i );

    stop: printf_s( "Jumped to stop. i = %d\n", i );
}
```

在此示例中，当 `i` 等于 5 时，`goto` 语句将控制权转移给标记为 `stop` 的点。

## <a name="see-also"></a>请参阅

[语句](../c-language/statements-c.md)
