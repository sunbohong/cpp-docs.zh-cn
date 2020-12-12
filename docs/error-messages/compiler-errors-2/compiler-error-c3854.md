---
description: 了解更多：编译器错误 C3854
title: 编译器错误 C3854
ms.date: 11/04/2016
f1_keywords:
- C3854
helpviewer_keywords:
- C3854
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
ms.openlocfilehash: f6c2399ff4c38cfbb306bd90e5bb5e96b34220eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328158"
---
# <a name="compiler-error-c3854"></a>编译器错误 C3854

"=" 左边的表达式的计算结果为函数。  (函数不是左值，因此无法分配给函数) 

无法重新初始化引用。 取消引用函数引用将生成一个函数，该函数是右值，不能分配。 因此，不能通过对函数的引用进行赋值。

下面的示例生成 C3854：

```cpp
// C3854.cpp
int afunc(int i)
{
   return i;
}

typedef int (& rFunc_t)(int);
typedef int (* pFunc_t)(int);

int main()
{
   rFunc_t rf = afunc;   // OK binding a reference to function
   pFunc_t pf = &afunc;   // OK initializing a pointer to function

   *pf = &afunc;   // C3854
   // try the following line instead
   // pf = &afunc;
   *rf = &afunc;   // C3854
}
```
