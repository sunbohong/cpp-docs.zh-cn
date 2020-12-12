---
description: 了解更多：编译器错误 C2571
title: 编译器错误 C2571
ms.date: 11/04/2016
f1_keywords:
- C2571
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
ms.openlocfilehash: 773cab05204e15a22a4412364bd8f89cddfd92ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208965"
---
# <a name="compiler-error-c2571"></a>编译器错误 C2571

"function"：虚函数不能在联合 "union" 中

联合是使用虚函数声明的。 只能在类或结构中声明虚函数。  可能的解决方法：

1. 将联合更改为类或结构。

1. 使函数不是虚拟的。

下面的示例生成 C2571：

```cpp
// C2571.cpp
// compile with: /c
union A {
   virtual void func1();   // C2571
   void func2();   // OK
};
```
