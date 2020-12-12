---
description: 了解更多：编译器错误 C3024
title: 编译器错误 C3024
ms.date: 11/04/2016
f1_keywords:
- C3024
helpviewer_keywords:
- C3024
ms.assetid: 1c031c28-ce37-4de3-aead-cfe76b261856
ms.openlocfilehash: 840cbb173e6dd9fe5f5ebe76076b75883849f934
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174294"
---
# <a name="compiler-error-c3024"></a>编译器错误 C3024

“schedule(runtime)”: 不允许使用 chunk_size 表达式

不能将值传递给 schedule 子句的运行时参数。

下面的示例生成 C3024：

```cpp
// C3024.cpp
// compile with: /openmp /link vcomps.lib
#include <stdio.h>
#include "omp.h"

int main() {
   int i;

   #pragma omp parallel for schedule(runtime, 10)   // C3024
   for (i = 0; i < 10; ++i) ;

   #pragma omp parallel for schedule(runtime)   // OK
   for (i = 0; i < 10; ++i) ;
}
```
