---
description: 详细了解：编译器警告 (等级 3) C4243
title: 编译器警告（等级 3）C4243
ms.date: 11/04/2016
f1_keywords:
- C4243
helpviewer_keywords:
- C4243
ms.assetid: ca72f9ad-ce0b-43a9-a68c-106e1f8b90ef
ms.openlocfilehash: af82629d3f7282dd3b649f8dc35ad8bbb84174b6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344180"
---
# <a name="compiler-warning-level-3-c4243"></a>编译器警告（等级 3）C4243

"转换类型" 转换已从 "type1" 转换为 "type2"，但不可访问

指向派生类的指针转换为指向基类的指针，但派生类继承具有私有或受保护访问权限的基类。

下面的示例生成 C4243：

```cpp
// C4243.cpp
// compile with: /W3
// C4243 expected
struct B {
   int f() {
      return 0;
   };
};

struct D : private B {};
struct E : public B {};

int main() {
   // Delete the following 2 lines to resolve.
   int (D::* d)() = (int(D::*)()) &B::f;
   d;

   int (E::* e)() = (int(E::*)()) &B::f; // OK
   e;
}
```
