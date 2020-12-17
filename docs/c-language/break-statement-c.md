---
description: 详细了解：break 语句 (C)
title: break 语句 (C)
ms.date: 11/04/2016
f1_keywords:
- break
helpviewer_keywords:
- break keyword [C]
ms.assetid: 015627c7-0924-49b2-a4d1-c77edf5eae6a
ms.openlocfilehash: 54f20de08661073a65ee0b8c50cf877e719aadcf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211643"
---
# <a name="break-statement-c"></a>break 语句 (C)

`break` 语句终止执行出现它的最近的封闭 `do`、`for`、`switch` 或 `while` 语句。 控制权将传递给已终止语句后面的语句。

## <a name="syntax"></a>语法

*jump-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**break ;**

`break` 语句经常用于终止 `switch` 语句中对特定情况的处理。 缺少封闭的迭代或 `switch` 语句会生成错误。

在嵌套语句中，`break` 语句只终止直接围住它的 `do`、`for`、`switch` 或 `while` 语句。 可以使用 `return` 或 `goto` 语句将控制权从嵌套结构转移出到其他地方。

下面的示例展示了 `break` 语句：

```C
#include <stdio.h>
int main() {
   char c;
   for(;;) {
      printf_s( "\nPress any key, Q to quit: " );

      // Convert to character value
      scanf_s("%c", &c);
      if (c == 'Q')
          break;
   }
} // Loop exits only when 'Q' is pressed
```

## <a name="see-also"></a>请参阅

[break 语句](../cpp/break-statement-cpp.md)
