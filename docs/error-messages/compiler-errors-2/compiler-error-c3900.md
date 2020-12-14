---
description: 了解更多：编译器错误 C3900
title: 编译器错误 C3900
ms.date: 11/04/2016
f1_keywords:
- C3900
helpviewer_keywords:
- C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
ms.openlocfilehash: 7b210eb6369b8953f36821d45690de8656113af2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238925"
---
# <a name="compiler-error-c3900"></a>编译器错误 C3900

"member"：不允许在当前范围内使用

属性块只能包含函数声明和内联函数定义。 属性块中不允许除函数之外的其他成员。 不允许使用 typedef、运算符或友元函数。 有关详细信息，请参阅 [property](../../extensions/property-cpp-component-extensions.md)。

事件定义只能包含访问方法和函数。

下面的示例生成 C3900：

```cpp
// C3900.cpp
// compile with: /clr
ref class X {
   property int P {
      void set(int);   // OK
      int i;   // C3900 variable declaration
   };
};
```

下面的示例生成 C3900：

```cpp
// C3900b.cpp
// compile with: /clr
using namespace System;
delegate void H();
ref class X {
   event H^ E {
      int m;   // C3900

      // OK
      void Test() {}

      void add( H^ h ) {}
      void remove( H^ h ) {}
      void raise( ) {}
   }
};
```
