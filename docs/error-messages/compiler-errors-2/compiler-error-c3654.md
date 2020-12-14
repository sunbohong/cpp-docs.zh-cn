---
description: 了解更多：编译器错误 C3654
title: 编译器错误 C3654
ms.date: 11/04/2016
f1_keywords:
- C3654
helpviewer_keywords:
- C3654
ms.assetid: 57d96e3f-6bbb-4eaa-934b-26c23b4ceb2e
ms.openlocfilehash: e3f5aee0031e398493b97e403159da64e891d2b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198279"
---
# <a name="compiler-error-c3654"></a>编译器错误 C3654

"text"：显式重写中有语法错误

显式重写中出现意外的字符串。 有关详细信息，请参阅 [显式重写](../../extensions/explicit-overrides-cpp-component-extensions.md)。

下面的示例生成 C3654：

```cpp
// C3654.cpp
// compile with: /clr /c
public ref struct B {
   virtual void f() = 0;
   virtual void g() = 0;
   virtual void h() = 0;
};

public ref struct Q : B {
   virtual void f() = B::f, 3 {}   // C3654
   // try the following line instead
   // virtual void g() = B::g, B::h {}
};
```
