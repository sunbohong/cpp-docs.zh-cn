---
description: 了解更多：编译器错误 C2600
title: 编译器错误 C2600
ms.date: 11/04/2016
f1_keywords:
- C2600
helpviewer_keywords:
- C2600
ms.assetid: cce11943-ea01-4bee-a7b0-b67d24ec6493
ms.openlocfilehash: fbd99cb50bc3afc748e1d3b2e954c584a7cef78b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120017"
---
# <a name="compiler-error-c2600"></a>编译器错误 C2600

"function"：不能定义编译器生成的特殊成员函数 (必须先在类中声明) 

在为类定义成员函数（如构造函数或析构函数）之前，必须在类中声明它们。 如果没有在类中声明，则编译器会生成默认的构造函数和析构函数（称为特殊成员函数）。 但是，如果在类中定义这些函数中没有匹配声明的函数，则编译器将检测到冲突。

若要修复此错误，请在类声明中，声明你在类声明以外定义的每个成员函数。

以下示例生成 C2600：

```cpp
// C2600.cpp
// compile with: /c
class C {};
C::~C() {}   // C2600

class D {
   D::~D();
};

D::~D() {}
```
