---
description: 了解更多：编译器错误 C2575
title: 编译器错误 C2575
ms.date: 11/04/2016
f1_keywords:
- C2575
helpviewer_keywords:
- C2575
ms.assetid: 9eb45706-37ef-4481-b373-6d193ba13634
ms.openlocfilehash: c08404ec3ce2d260d19b9889b668c0d98db265b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208874"
---
# <a name="compiler-error-c2575"></a>编译器错误 C2575

"identifier"：只有成员函数和基可以是虚拟的

声明全局函数或类 **`virtual`** 。 这是不允许的。

下面的示例生成 C2575：

```cpp
// C2575.cpp
// compile with: /c
virtual void func() {}   // C2575

void func2() {}
struct A {
   virtual void func2(){}
};
```
