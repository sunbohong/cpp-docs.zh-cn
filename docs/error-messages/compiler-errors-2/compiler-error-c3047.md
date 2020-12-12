---
description: 了解更多：编译器错误 C3047
title: 编译器错误 C3047
ms.date: 11/04/2016
f1_keywords:
- C3047
helpviewer_keywords:
- C3047
ms.assetid: 91c14566-5958-433d-8549-0e8bc3196f76
ms.openlocfilehash: 471f85f6a73e911ea9c308a3de9d2afbe800f750
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269778"
---
# <a name="compiler-error-c3047"></a>编译器错误 C3047

OpenMP“sections”区域中的结构化块的前面必须是“#pragma omp section”

[sections](../../parallel/openmp/reference/openmp-directives.md#sections-openmp) 指令所引入代码块中的任何代码必须位于 `section` 指令引入的代码块中。

下面的示例生成 C3047：

```cpp
// C3047.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
      {

         #pragma omp section
         {
            ++n3;
         }

         ++n2;   // C3047 not enclosed in #pragma omp section
      }
   }
}
```
