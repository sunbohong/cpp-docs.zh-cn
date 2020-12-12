---
description: 了解更多：编译器错误 C3668
title: 编译器错误 C3668
ms.date: 11/04/2016
f1_keywords:
- C3668
helpviewer_keywords:
- C3668
ms.assetid: 53a96698-bde4-4447-95b5-b5108291f60c
ms.openlocfilehash: a13de2f8ea1ca9c8bf6d66483c777d74675fef9e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269492"
---
# <a name="compiler-error-c3668"></a>编译器错误 C3668

"method"：重写说明符 "override" 的方法没有重写任何基类方法

函数试图重写不存在的函数。

有关详细信息，请参阅 [显式重写](../../extensions/explicit-overrides-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例生成 C3668。

```cpp
// C3668.cpp
// compile with: /c
__interface I {
   void f(int);   // virtual by default
};

class J {
public:
   void g(int);
   virtual void h(int);
};

struct R : I,J {
   virtual void f() override {}   // C3668
   virtual void f(int) override {}   // OK

   virtual void g(int) override {}   // C3668
   virtual void h(int) override {}   // OK
};
```
