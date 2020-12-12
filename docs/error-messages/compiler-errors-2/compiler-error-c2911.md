---
description: 了解更多：编译器错误 C2911
title: 编译器错误 C2911
ms.date: 11/04/2016
f1_keywords:
- C2911
helpviewer_keywords:
- C2911
ms.assetid: 83c7c01a-ab6a-4179-9fb0-289a9ec8d44e
ms.openlocfilehash: c3890a6017e96b4b5f2f9dc7b5711fd98f29b947
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270533"
---
# <a name="compiler-error-c2911"></a>编译器错误 C2911

“member”: 无法在当前范围中声明或定义

在命名空间、类或函数内部，只能定义同一命名空间、类或函数的成员，或者由同一命名空间、类或函数括起的成员。

以下示例生成 C2911：

```cpp
// C2911.cpp
struct A;

namespace M {
   struct D;
}

namespace N {
   struct C;

   namespace O {
      struct B;
   }

   // in N
   struct ::A {};   // C2911  A is member of global NS
   struct O::B{};   // OK B is in O, O is inside of N
   struct C {};     // OK C is member of N
   struct M::D {};  // C2911 D is member of M, M not enclosed by N
}
```
