---
title: 编译器错误 C3918
ms.date: 11/04/2016
f1_keywords:
- C3918
helpviewer_keywords:
- C3918
ms.assetid: a8b3a90a-3fe1-4244-a5ff-a31cdae97d98
ms.openlocfilehash: cd9c40ef90715e9beca43a114dba475ab29b5e78
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686033"
---
# <a name="compiler-error-c3918"></a>编译器错误 C3918

用法要求 "member" 是数据成员

与事件相关的多种原因可能会导致 C3918。

## <a name="examples"></a>示例

由于当前上下文需要类成员，因此可能会发生 C3918。 下面的示例生成 C3918。

```cpp
// C3918.cpp
// compile with: /clr /c
public ref class C {
public:
   System::Object ^ o;
   delegate void Del();

   event Del^ MyEvent {
      void add(Del^ev) {
         if ( MyEvent != nullptr) {}   // C3918
         if ( o != nullptr) {}   // OK
   }
   void remove(Del^){}
   }
};
```

如果尝试检查简单事件的 null (事件名称将不再提供对事件) 的后备存储委托的直接访问权限，则也会导致 C3918。

下面的示例生成 C3918。

```cpp
// C3918_2.cpp
// compile with: /clr /c
using namespace System;
public delegate int MyDel(int);

interface struct IEFace {
   event MyDel ^ E;
};

ref struct EventSource : public IEFace {
   virtual event MyDel ^ E;
   void Fire_E(int i) {
      if (E)   // C3918
         E(i);
   }
};
```

如果未正确订阅事件，也会发生 C3918。 下面的示例生成 C3918。

```cpp
// C3918_3.cpp
// compile with: /clr /c
using namespace System;

public delegate void del();

public ref class A {
public:
   event del^ e {
      void add(del ^handler ) {
         d += handler;
      }

      void remove(del ^handler) {
         d -= handler;
      }

      void raise() {
         d();
      }
   }

   del^ d;
   void f() {}

   A() {
      e = gcnew del(this, &A::f);   // C3918
      // try the following line instead
      // e += gcnew del(this, &A::f);
      e();
   }
};

int main() {
   A a;
}
```
