---
description: 了解详细信息：编译器警告 (等级 1) C4374
title: 编译器警告（等级 1）C4374
ms.date: 11/04/2016
f1_keywords:
- C4374
helpviewer_keywords:
- C4374
ms.assetid: 4ac9aaec-d815-4b6e-825f-fa872092dd3b
ms.openlocfilehash: 0b1d8eef5f168f12cc41f1108fcea24040f806ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311328"
---
# <a name="compiler-warning-level-1-c4374"></a>编译器警告（等级 1）C4374

"function1"：接口方法不能由非虚方法 "function2" 实现

编译器需要在方法定义中查找 [虚](../../cpp/virtual-specifier.md) 关键字。

下面的示例生成 C4374：

```cpp
// C4374.cpp
// compile with: /clr /W1 /c /WX
public interface class I {
   void f();
};

public ref struct B {
   void f() {
      System::Console::WriteLine("B::f()");
   }
};

public ref struct C {
   virtual void f() {
      System::Console::WriteLine("C::f()");
   }
};

public ref struct D : B, I {};   // C4374
public ref struct E : C, I {};   // OK
```
