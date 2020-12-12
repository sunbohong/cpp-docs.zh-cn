---
description: 了解更多：编译器错误 C3055
title: 编译器错误 C3055
ms.date: 11/04/2016
f1_keywords:
- C3055
helpviewer_keywords:
- C3055
ms.assetid: 60446ee0-18dd-48fc-9059-f0a14229dce8
ms.openlocfilehash: 6c75d476abf7535499c74705e4a0ec77d80dc772
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269570"
---
# <a name="compiler-error-c3055"></a>编译器错误 C3055

“symbol”：符号在用于“threadprivate”指令之前无法引用

引用了一个符号，然后在 [threadprivate](../../parallel/openmp/reference/openmp-directives.md#threadprivate) 子句中使用，这是不允许的。

下面的示例生成 C3055：

```cpp
// C3055.cpp
// compile with: /openmp
int x, y;
int z = x;
#pragma omp threadprivate(x, y)   // C3055

void test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

可能的解决方法：

```cpp
// C3055b.cpp
// compile with: /openmp /LD
int x, y, z;
#pragma omp threadprivate(x, y)

void test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```
