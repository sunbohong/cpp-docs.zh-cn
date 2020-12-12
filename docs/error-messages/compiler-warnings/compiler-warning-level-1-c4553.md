---
description: 了解详细信息：编译器警告 (等级 1) C4553
title: 编译器警告（等级 1）C4553
ms.date: 11/04/2016
f1_keywords:
- C4553
helpviewer_keywords:
- C4553
ms.assetid: d8aacbe0-3cb5-4367-a6e5-fd7e28f0ff9d
ms.openlocfilehash: 93d775e1a91f8306240824f99da1fae107963696
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265891"
---
# <a name="compiler-warning-level-1-c4553"></a>编译器警告（等级 1）C4553

"operator"：运算符不起任何作用;您是否打算 "operator"？

如果表达式语句的运算符没有副作用作为表达式的顶部，则这可能是错误的。

下面的示例生成 C4553：

```cpp
// C4553.cpp
// compile with: /W1
int func()
{
   return 0;
}

int main()
{
   int i;
   i == func();   // C4553
   // try the following line instead
   // i = func();
}
```
