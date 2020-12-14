---
description: 了解更多：编译器错误 C3736
title: 编译器错误 C3736
ms.date: 11/04/2016
f1_keywords:
- C3736
helpviewer_keywords:
- C3736
ms.assetid: 579b773c-41e7-40ea-8382-2e3ce2667f4c
ms.openlocfilehash: 6ec22012efb9de3ec7f0b8911ed45f4f6a724135
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244987"
---
# <a name="compiler-error-c3736"></a>编译器错误 C3736

"event"：必须是方法，在托管事件中也可以是数据成员

本机事件和 COM 事件必须是方法。 .NET 事件也可以是数据成员。

下面的示例生成 C3736：

```cpp
// C3736.cpp
struct A {
   __event int e();
};

struct B {
   int f;   // C3736
   // The following line resolves the error.
   // int f();
   B(A* a) {
      __hook(&A::e, a, &B::f);
   }
};

int main() {
}
```
