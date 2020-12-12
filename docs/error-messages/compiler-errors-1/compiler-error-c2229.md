---
description: 了解更多：编译器错误 C2229
title: 编译器错误 C2229
ms.date: 11/04/2016
f1_keywords:
- C2229
helpviewer_keywords:
- C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
ms.openlocfilehash: d95d1248ec7e555af0c4ecfffa25dc69af288458
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194977"
---
# <a name="compiler-error-c2229"></a>编译器错误 C2229

类型 "identifier" 具有非法的零大小的数组

结构或位域的成员包含大小为零的数组，该数组不是最后一个成员。

由于可以将零大小的数组作为结构的最后一个成员，因此，在分配结构时必须指定其大小。

如果大小为零的数组不是结构的最后一个成员，则编译器不能计算剩余字段的偏移量。

下面的示例生成 C2229：

```cpp
// C2229.cpp
struct S {
   int a[0];  // C2229  zero-sized array
   int b[1];
};

struct S2 {
   int a;
   int b[0];
};

int main() {
   // allocate 7 elements for b field
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];
   s2->b[6] = 100;
}
```
