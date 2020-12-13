---
description: 详细了解：编译器警告 (等级 3) C4197
title: 编译器警告 (等级 3) C4197
ms.date: 11/04/2016
f1_keywords:
- C4197
helpviewer_keywords:
- C4197
ms.assetid: f766feef-82b0-4d81-8a65-33628c7db196
ms.openlocfilehash: f52c37e28ce681b96158b7e1f10fef3e9f121522
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344206"
---
# <a name="compiler-warning-level-3-c4197"></a>编译器警告 (等级 3) C4197

"type"：忽略强制转换中的顶级 volatile

编译器检测到对使用 [volatile](../../cpp/volatile-cpp.md)限定的 r 值类型的强制转换，或对使用 volatile 限定的某种类型的 r 值类型的强制转换。 根据 C 标准 (6.5.3) ，与限定类型关联的属性仅对左值表达式有意义。

下面的示例生成 C4197：

```cpp
// C4197.cpp
// compile with: /W3
#include <stdio.h>
#include <signal.h>
#include <stdlib.h>

void sigproc(int);
struct S
{
   int i;
} s;

int main()
{
   signal(SIGINT, sigproc);
   s.i = 1;
   S *pS = &s;
   for ( ; (volatile int)pS->i ; )   // C4197
      break;
   // for ( ; *(volatile int *)&pS->i ; )   // OK
   //    break;
}

void sigproc(int) // ctrl-C
{
   signal(SIGINT, sigproc);
   s.i = 0;
}
```
