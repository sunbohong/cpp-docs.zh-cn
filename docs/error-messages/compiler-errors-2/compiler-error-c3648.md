---
description: 了解更多：编译器错误 C3648
title: 编译器错误 C3648
ms.date: 11/04/2016
f1_keywords:
- C3648
helpviewer_keywords:
- C3648
ms.assetid: 5d042989-41cb-4cd0-aa50-976b70146aaf
ms.openlocfilehash: 532c65896ae5c3707c86735c661a095698417288
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203739"
---
# <a name="compiler-error-c3648"></a>编译器错误 C3648

此显式重写语法需要/clr： oldSyntax

当针对最新的托管语法进行编译时，编译器找到了不再受支持的以前版本的显式重写语法。

有关详细信息，请参阅 [显式重写](../../extensions/explicit-overrides-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例生成 C3648：

```cpp
// C3648.cpp
// compile with: /clr
public interface struct I {
   void f();
};

public ref struct R : I {
   virtual void I::f() {}   // C3648
   // try the following line instead
   // virtual void f() = I::f{}
};
```
