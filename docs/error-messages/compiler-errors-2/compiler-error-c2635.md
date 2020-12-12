---
description: 了解更多：编译器错误 C2635
title: 编译器错误 C2635
ms.date: 11/04/2016
f1_keywords:
- C2635
helpviewer_keywords:
- C2635
ms.assetid: 9deca2a8-2d61-42eb-9783-6578132ee3fb
ms.openlocfilehash: 8ecc6faaefb3dea5f0cfcded4d6817a807580254
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123378"
---
# <a name="compiler-error-c2635"></a>编译器错误 C2635

无法将 "identifier1 *" 转换为 "identifier2 \* "; 暗含了从虚拟基类的转换

转换需要从基类强制转换 **`virtual`** 为派生类，这是不允许的。

下面的示例生成 C2635：

```cpp
// C2635.cpp
class B {};
class D : virtual public B {};
class E : public B {};

int main() {
   B b;
   D d;
   E e;

   D * pD = &d;
   E * pE = &e;
   pD = (D*)&b;   // C2635
   pE = (E*)&b;   // OK
}
```
