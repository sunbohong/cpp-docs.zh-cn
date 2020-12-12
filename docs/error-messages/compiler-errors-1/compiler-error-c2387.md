---
description: 了解更多：编译器错误 C2387
title: 编译器错误 C2387
ms.date: 11/04/2016
f1_keywords:
- C2387
helpviewer_keywords:
- C2387
ms.assetid: 6847b8e1-ffac-458d-ab88-0c92f72f2527
ms.openlocfilehash: 70c876c999ec7d40b93ac94ffe111d105981ceeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124002"
---
# <a name="compiler-error-c2387"></a>编译器错误 C2387

"type"：不明确的基类

编译器无法明确解析函数调用，因为该函数存在于多个基类中。

若要解决此错误，请从继承中移除一个基类，或显式限定函数调用。

下面的示例生成 C2387：

```cpp
// C2387.cpp
namespace N1 {
   struct B {
      virtual void f() {
      }
   };
}

namespace N2 {
   struct B {
      virtual void f() {
      }
   };
}

struct D : N1::B, N2::B {
   virtual void f() {
      B::f();   // C2387
      // try the following line instead
      // N1::B::f();
   }
};

int main() {
   D aD;
   aD.f();
}
```
