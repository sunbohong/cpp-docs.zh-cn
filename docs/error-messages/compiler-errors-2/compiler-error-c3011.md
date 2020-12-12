---
description: 了解更多：编译器错误 C3011
title: 编译器错误 C3011
ms.date: 11/04/2016
f1_keywords:
- C3011
helpviewer_keywords:
- C3011
ms.assetid: 24c3a917-ebff-4deb-9155-23adf6468531
ms.openlocfilehash: 3a8591ad528c68bb5d072049e2b85567699fc5c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286028"
---
# <a name="compiler-error-c3011"></a>编译器错误 C3011

并行区域内不允许直接使用内联程序集

`omp` 并行区域不能包含内联程序集指令。

下面的示例生成 C3011：

```cpp
// C3011.cpp
// compile with: /openmp
// processor: /x86
int main() {
   int   n = 0;

   #pragma omp parallel
   {
      _asm mov eax, n   // Delete this line to resolve this error.
   }   // C3011
}
```
