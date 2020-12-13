---
description: 了解更多：编译器错误 C2885
title: 编译器错误 C2885
ms.date: 11/04/2016
f1_keywords:
- C2885
helpviewer_keywords:
- C2885
ms.assetid: 7743e5f3-a034-44b4-9ee8-5a6254c27f8c
ms.openlocfilehash: 040f7a151c34fe7b5e30b6aad1e5bc956b3e5cf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337489"
---
# <a name="compiler-error-c2885"></a>编译器错误 C2885

"class：： identifier"：在非类范围内不是有效的 using 声明

[使用](../../cpp/using-declaration.md)的声明不正确。

此错误可能是由于对 Visual Studio 2005 执行的编译器一致性工作所导致的，因为对 **`using`** 嵌套类型的声明不再有效; 您必须显式限定对嵌套类型的每个引用，将该类型放入命名空间中，或创建一个 typedef。

## <a name="examples"></a>示例

下面的示例生成 C2885。

```cpp
// C2885.cpp
namespace MyNamespace {
   class X1 {};
}

struct MyStruct {
   struct X1 {
      int i;
   };
};

int main () {
   using MyStruct::X1;   // C2885

   // OK
   using MyNamespace::X1;
   X1 myX1;

   MyStruct::X1 X12;

   typedef MyStruct::X1 abc;
   abc X13;
   X13.i = 9;
}
```

如果将关键字用于 **`using`** 类成员，c + + 要求在) 派生类 (的其他类中定义该成员。

下面的示例生成 C2885。

```cpp
// C2885_b.cpp
// compile with: /c
class A {
public:
   int i;
};

void z() {
   using A::i;   // C2885 not in a class
}

class B : public A {
public:
   using A::i;
};
```
