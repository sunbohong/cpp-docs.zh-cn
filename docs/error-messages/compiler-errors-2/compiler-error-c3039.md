---
title: 编译器错误 C3039
ms.date: 11/04/2016
f1_keywords:
- C3039
helpviewer_keywords:
- C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
ms.openlocfilehash: ea6efbfa95992b04ade5496e8c7253ee87319a93
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508368"
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
