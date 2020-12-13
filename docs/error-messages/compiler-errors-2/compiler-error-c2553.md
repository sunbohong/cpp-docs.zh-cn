---
description: 了解更多：编译器错误 C2553
title: 编译器错误 C2553
ms.date: 11/04/2016
f1_keywords:
- C2553
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
ms.openlocfilehash: 5f5e3eb9d94935aa8e6974f72517e7193ba07db3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134493"
---
# <a name="compiler-error-c2553"></a>编译器错误 C2553

"base_function"：重写虚函数返回类型与 "override_function" 不同

派生类中的函数尝试重写基类中的虚函数，但该派生类函数的返回类型与基类函数的返回类型不同。  重写函数签名必须与被重写的函数的签名匹配。

下面的示例生成 C2553：

```cpp
// C2553.cpp
// compile with: /clr /c
ref struct C {
   virtual void f();
};

ref struct D : C {
   virtual int f() override ;   // C2553

   // try the following line instead
   // virtual void f() override;
};
```
