---
description: 了解更多：编译器错误 C3052
title: 编译器错误 C3052
ms.date: 11/04/2016
f1_keywords:
- C3052
helpviewer_keywords:
- C3052
ms.assetid: 87480c42-1ceb-4775-8d20-88c54a7bb6a6
ms.openlocfilehash: d9d4ecf6082de02c3a4cec6486b2718a101b22d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269648"
---
# <a name="compiler-error-c3052"></a>编译器错误 C3052

“var”: default(none) 子句下的 data-sharing 子句中未出现变量

若使用 [default (none)](../../parallel/openmp/reference/openmp-clauses.md#default-openmp) ，则结构化块中使用的任何变量均必须显式指定为 [shared](../../parallel/openmp/reference/openmp-clauses.md#shared-openmp) 或 [private](../../parallel/openmp/reference/openmp-clauses.md#private-openmp)。

下面的示例生成 C3052：

```cpp
// C3052.cpp
// compile with: /openmp /c
int main() {
   int n1 = 1;

   #pragma omp parallel default(none) // shared(n1) private(n1)
   {
      n1 = 0;   // C3052 use either a shared or private clause
   }
}
```
