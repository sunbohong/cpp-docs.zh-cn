---
description: 了解更多：编译器错误 C2352
title: 编译器错误 C2352
ms.date: 11/04/2016
f1_keywords:
- C2352
helpviewer_keywords:
- C2352
ms.assetid: 0efad8cb-659f-4b3e-8f6f-9f8ec44d345c
ms.openlocfilehash: f8094261c4a0ad23b5603d1e16bbaa4f34e0038e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298300"
---
# <a name="compiler-error-c2352"></a>编译器错误 C2352

“class::function”：非静态成员函数的非法调用

**`static`** 称为非静态成员函数的成员函数。 或者，从类外部将非静态成员函数作为静态函数进行了调用。

下面的示例生成 C2352，并演示如何修复此错误：

```cpp
// C2352.cpp
// compile with: /c
class CMyClass {
public:
   static void func1();
   void func2();
   static void func3() {
      func2();   // C2352 calls nonstatic func2
      func1();   // OK calls static func1
   }
};
```

下面的示例生成 C2352，并演示如何修复此错误：

```cpp
// C2352b.cpp
class MyClass {
public:
   void MyFunc() {}
   static void MyFunc2() {}
};

int main() {
   MyClass::MyFunc();   // C2352
   MyClass::MyFunc2();   // OK
}
```
