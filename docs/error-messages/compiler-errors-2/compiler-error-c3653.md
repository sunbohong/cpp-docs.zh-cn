---
description: 了解更多：编译器错误 C3653
title: 编译器错误 C3653
ms.date: 11/04/2016
f1_keywords:
- C3653
helpviewer_keywords:
- C3653
ms.assetid: 316549d7-f7ef-4578-a2ba-57adc8aac527
ms.openlocfilehash: 6f41d52416d2fee05873197efa60e4b888cf29f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320100"
---
# <a name="compiler-error-c3653"></a>编译器错误 C3653

"function"：不能用作命名重写：未找到正在被重写的函数;您是否忘记了使用：：运算符显式命名该函数？

显式重写指定了在任何接口中都找不到的函数。 有关详细信息，请参阅 [显式重写](../../extensions/explicit-overrides-cpp-component-extensions.md)。

下面的示例生成 C3653：

```cpp
// C3653.cpp
// compile with: /clr
public interface struct I {
   void h();
};

public ref struct X : public I {
   virtual void f() new sealed = J {};   // C3653 no J in scope
   virtual void g() {}   // OK
   virtual void h() new sealed = I::h {};   // OK
};
```
