---
description: 了解更多：编译器错误 C3039
title: 编译器错误 C3039
ms.date: 11/04/2016
f1_keywords:
- C3039
helpviewer_keywords:
- C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
ms.openlocfilehash: e84f769e49fa2b06eea2b1fe0b53ea2d935efb9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270012"
---
# <a name="compiler-error-c3039"></a>编译器错误 C3039

“var”: OpenMP “for”语句中索引变量不能是 reduction 变量

索引变量是隐式私有变量，因此该变量不能用于一组 [parallel](../../parallel/openmp/reference/openmp-clauses.md#reduction) 指令中的 [reduction](../../parallel/openmp/reference/openmp-directives.md#parallel) 子句。

## <a name="example"></a>示例

以下示例生成 C3039:

```cpp
// C3039.cpp
// compile with: /openmp /c
int g_i;

int main() {
   int i;

   #pragma omp parallel reduction(+: i)
   {
      #pragma omp for
      for (i = 0; i < 10; ++i)   // C3039
         g_i += i;
   }
}
```
