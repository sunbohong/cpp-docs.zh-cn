---
description: 了解更多：编译器错误 C3018
title: 编译器错误 C3018
ms.date: 11/04/2016
f1_keywords:
- C3018
helpviewer_keywords:
- C3018
ms.assetid: 685be45f-f116-43a8-a88d-05ab6616e2f1
ms.openlocfilehash: cb2b144a09edc4dbe64f4940e476cca0f73c585b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285820"
---
# <a name="compiler-error-c3018"></a>编译器错误 C3018

“var1”: OpenMP“for”测试或递增必须使用索引变量“var2”

**`for`** OpenMP 语句中的循环必须使用相同的变量进行测试，并在其索引时使用增量。

下面的示例生成 C3018:

```cpp
// C3018.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 5;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; j < 10; ++i)   // C3018
      // try the following line instead
      // for (i = 0; i < 10; ++i)
         j *= 2;

      #pragma omp for
      for (i = 0; i < 10; j = j + i)   // C3018
      // try the following line instead
      // for (i = 0; i < 10; i = j + i)
         j *= 2;
   }
}
```
