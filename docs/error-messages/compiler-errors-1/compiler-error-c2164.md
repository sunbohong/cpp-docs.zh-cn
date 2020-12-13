---
description: 了解更多：编译器错误 C2164
title: 编译器错误 C2164
ms.date: 11/04/2016
f1_keywords:
- C2164
helpviewer_keywords:
- C2164
ms.assetid: 55df5024-68a8-45a8-ae6c-e6dba35318a2
ms.openlocfilehash: 9afe0809075f83c77ffae2ef77bc72c9e0f194e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145506"
---
# <a name="compiler-error-c2164"></a>编译器错误 C2164

"function"：未声明的内部函数

`intrinsic`杂注使用未声明的函数 (仅在 **/Oi**) 时发生。 或者，使用了编译器内部函数之一，而不包括其标头文件。

下面的示例生成 C2164：

```c
// C2164.c
// compile with: /c
// processor: x86
// Uncomment the following line to resolve.
// #include "xmmintrin.h"
void b(float *p) {
   _mm_load_ss(p);   // C2164
}
```
