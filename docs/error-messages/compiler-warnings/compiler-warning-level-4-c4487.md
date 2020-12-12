---
description: 详细了解：编译器警告 (级别 4) C4487
title: 编译器警告（等级 4）C4487
ms.date: 11/04/2016
f1_keywords:
- C4487
helpviewer_keywords:
- C4487
ms.assetid: 796144cf-cd3c-4edc-b6a4-96192b7eb4f0
ms.openlocfilehash: a750152e6920f9e012f3a1b7d093b68749e6fe8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203466"
---
# <a name="compiler-warning-level-4-c4487"></a>编译器警告（等级 4）C4487

"derived_class_function"：匹配继承的非虚方法 "base_class_function"，但没有显式标记为 "new"

派生类中的函数与非虚拟基类函数具有相同的签名。 C4487 提醒你派生类函数不会重写基类函数。 将派生类函数显式标记为 **`new`** ，以解决此警告。

有关详细信息，请参阅 [) 中的新 (新槽 ](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例生成 C4487。

```cpp
// C4487.cpp
// compile with: /W4 /clr
using namespace System;
public ref struct B {
   void f() { Console::WriteLine("in B::f"); }
   void g() { Console::WriteLine("in B::g"); }
};

public ref struct D : B {
   void f() { Console::WriteLine("in D::f"); }   // C4487
   void g() new { Console::WriteLine("in D::g"); }   // OK
};

int main() {
   B ^ a = gcnew D;
   // will call base class functions
   a->f();
   a->g();
}
```
