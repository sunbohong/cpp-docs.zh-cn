---
description: 了解更多：编译器错误 C2583
title: 编译器错误 C2583
ms.date: 11/04/2016
f1_keywords:
- C2583
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
ms.openlocfilehash: 067e65f6085d033ca8d7372ee5e4d169e1b411dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177687"
---
# <a name="compiler-error-c2583"></a>编译器错误 C2583

"identifier"： "const/volatile" "this" 指针对于构造函数/析构函数是非法的

构造函数或析构函数被声明为 **`const`** 或 **`volatile`** 。 这是不允许的。

下面的示例生成 C2583：

```cpp
// C2583.cpp
// compile with: /c
class A {
public:
   int i;
   A() const;   // C2583

   // try the following line instead
   // A();
};
```
