---
description: 了解更多：编译器错误 C2550
title: 编译器错误 C2550
ms.date: 11/04/2016
f1_keywords:
- C2550
helpviewer_keywords:
- C2550
ms.assetid: 3293f53e-ee66-4035-920d-34e115c3a24c
ms.openlocfilehash: 046cb88be2dfdb0e73273a7c370d6d7fdd97243f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204077"
---
# <a name="compiler-error-c2550"></a>编译器错误 C2550

"identifier"：构造函数初始值设定项列表只能在构造函数定义中使用

基类初始值设定项列表用于不是构造函数的函数的定义。

下面的示例生成 C2550：

```cpp
// C2550.cpp
// compile with: /c
class C {
public:
   C();
};

class D : public C {
public:
   D();
   void func();
};

void D::func() : C() {}  // C2550
D::D() : C() {}   // OK
```
