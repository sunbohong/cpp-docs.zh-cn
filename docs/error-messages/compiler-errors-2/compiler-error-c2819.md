---
description: 了解更多：编译器错误 C2819
title: 编译器错误 C2819
ms.date: 11/04/2016
f1_keywords:
- C2819
helpviewer_keywords:
- C2819
ms.assetid: fcc7762d-cb82-4bb1-a715-0d82da832edf
ms.openlocfilehash: fa30432399913c6bdd00bb2728931d213c14064c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194743"
---
# <a name="compiler-error-c2819"></a>编译器错误 C2819

类型 "type" 没有重载成员 "operator->"

需要将定义 `operator->()` 为使用此指针运算。

下面的示例生成 C2819：

```cpp
// C2819.cpp
// compile with: /c
class A {
   public:
      int i;
};

class B {};

void C(B j) {
   j->i;   // C2819
}

class D {
   A* pA;

   public:
      A* operator->() {
         return pA;
      }
};

void F(D j) {
   j->i;
}
```

当 [对引用类型使用 c + + 堆栈语义时，](../../dotnet/cpp-stack-semantics-for-reference-types.md)也会发生 C2819。 下面的示例生成 C2819：

```cpp
// C2819_b.cpp
// compile with: /clr
ref struct R {
   void Test() {}
};

int main() {
   R r;
   r->Test();   // C2819
   r.Test();   // OK
}
```
