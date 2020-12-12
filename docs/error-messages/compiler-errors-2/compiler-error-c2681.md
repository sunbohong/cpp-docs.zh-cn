---
description: 了解更多：编译器错误 C2681
title: 编译器错误 C2681
ms.date: 11/04/2016
f1_keywords:
- C2681
helpviewer_keywords:
- C2681
ms.assetid: eb42da6d-8d2c-43fd-986b-e73e2b004885
ms.openlocfilehash: 3b002e6260787e60377d726bcceb6db41fce532a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267776"
---
# <a name="compiler-error-c2681"></a>编译器错误 C2681

"type"：名称的表达式类型无效

转换运算符尝试从无效的类型转换。 例如，如果使用 [dynamic_cast](../../cpp/dynamic-cast-operator.md) 运算符将表达式转换为指针类型，则源表达式必须是指针。

下面的示例生成 C2681：

```cpp
// C2681.cpp
class A { virtual void f(); };

void g(int i) {
    A* pa;
    pa = dynamic_cast<A*>(i);  // C2681
}
```
