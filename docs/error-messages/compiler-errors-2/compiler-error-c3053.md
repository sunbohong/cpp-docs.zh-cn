---
description: 了解更多：编译器错误 C3053
title: 编译器错误 C3053
ms.date: 11/04/2016
f1_keywords:
- C3053
helpviewer_keywords:
- C3053
ms.assetid: ab9a25f3-e341-4f6e-8e69-069b4a963a64
ms.openlocfilehash: 8f42d3301ae5980942d33cefc90c74a5a0d39b16
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269622"
---
# <a name="compiler-error-c3053"></a>编译器错误 C3053

“symbol”: “threadprivate”只对全局或静态数据项有效

传递给 [threadprivate](../../parallel/openmp/reference/openmp-directives.md#threadprivate) 的符号必须是全局或静态的。

以下示例生成 C3053：

```cpp
// C3053.cpp
// compile with: /openmp
void Test() {
   int x, y;
   #pragma omp threadprivate(x, y)   // C3053
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

可能的解决方法：

```cpp
// C3053b.cpp
// compile with: /openmp /LD
int x, y;
#pragma omp threadprivate(x, y)

void Test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```
