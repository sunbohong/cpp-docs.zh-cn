---
description: 了解更多：编译器错误 C3042
title: 编译器错误 C3042
ms.date: 11/04/2016
f1_keywords:
- C3042
helpviewer_keywords:
- C3042
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
ms.openlocfilehash: 04c4366e574f158234653d32b4b6e01bfceaaa27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269908"
---
# <a name="compiler-error-c3042"></a>编译器错误 C3042

“copyprivate”和“nowait”子句不能同时出现在 OpenMP“directive”指令中

[Copyprivate](../../parallel/openmp/reference/openmp-clauses.md#copyprivate) 和 [nowait](../../parallel/openmp/reference/openmp-clauses.md#nowait) 子句在指定的指令上彼此排斥。 若要修复此错误，请删除 `copyprivate` 或 `nowait` 子句之一或两者一起删除。

以下示例生成 C3042：

```cpp
// C3042.cpp
// compile with: /openmp /c
#include <stdio.h>
#include "omp.h"

double d;

int main() {
    #pragma omp parallel private(d)
   {
      #pragma omp single copyprivate(d) nowait   // C3042
      {
      }
   }
}
```
