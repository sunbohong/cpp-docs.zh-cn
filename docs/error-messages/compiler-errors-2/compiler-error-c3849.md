---
description: 了解更多：编译器错误 C3849
title: 编译器错误 C3849
ms.date: 11/04/2016
f1_keywords:
- C3849
helpviewer_keywords:
- C3849
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
ms.openlocfilehash: 6dbe4656eea2691c1c77c1afa389be80ab76af18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255348"
---
# <a name="compiler-error-c3849"></a>编译器错误 C3849

"type" 类型的表达式中的函数样式调用会丢失所有可用的可用运算符重载的 const 和/或 volatile 限定符

具有指定 const volatile 类型的变量只能调用使用相同或更大的 const volatile 限定定义的成员函数。

若要修复此错误，请提供相应的成员函数。 当转换导致无法进行限定时，不能对 const 或 volatile 限定对象执行转换。 可以获取限定符，但不能在转换中丢失限定符。

以下示例生成 C3849：

```cpp
// C3849.cpp
void glbFunc3(int i, char c)
{
   i;
}
typedef void (* pFunc3)(int, char);

void glbFunc2(int i)
{
   i;
}

typedef void (* pFunc2)(int);

void glbFunc1()
{
}
typedef void (* pFunc1)();

struct S4
{
   operator ()(int i)
   {
      i;
   }

   operator pFunc1() const
   {
      return &glbFunc1;
   }

   operator pFunc2() volatile
   {
      return &glbFunc2;
   }

   operator pFunc3()
   {
      return &glbFunc3;
   }

   // operator pFunc1() const volatile
   // {
   //    return &glbFunc1;
   // }
};

int main()
{
   // Cannot call any of the 4 overloads of "operator ()(.....)" and
   // "operator pFunc()" because none is declared as "const volatile"
   const volatile S4 s4;  // can only call cv member functions of S4
   s4();   // C3849 to resolve, uncomment member function
}
```
