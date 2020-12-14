---
description: 了解更多：编译器错误 C3671
title: 编译器错误 C3671
ms.date: 11/04/2016
f1_keywords:
- C3671
helpviewer_keywords:
- C3671
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
ms.openlocfilehash: a8fba0ccec84789b7fe5e45cd72b18abc3fe63b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228867"
---
# <a name="compiler-error-c3671"></a>编译器错误 C3671

"function_1"：函数没有重写 "function_2"

使用显式 override 语法时，如果未重写函数，编译器将生成错误。  有关详细信息，请参阅 [显式重写](../../extensions/explicit-overrides-cpp-component-extensions.md) 。

## <a name="example"></a>示例

下面的示例生成 C3671。

```cpp
// C3671.cpp
// compile with: /clr /c
ref struct S {
   virtual void f();
};

ref struct S1 : S {
   virtual void f(int) new sealed = S::f;   // C3671
   virtual void f() new sealed = S::f;
};
```
