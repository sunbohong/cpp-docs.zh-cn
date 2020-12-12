---
description: 了解更多：编译器错误 C3255
title: 编译器错误 C3255
ms.date: 11/04/2016
f1_keywords:
- C3255
helpviewer_keywords:
- C3255
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
ms.openlocfilehash: 576b2c9126173f72470a6e741dd64d8a356c9224
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194197"
---
# <a name="compiler-error-c3255"></a>编译器错误 C3255

"值类型"：在本机堆上无法动态分配此值类型对象

值类型 (的实例（) 包含托管成员的 [类和结构](../../extensions/classes-and-structs-cpp-component-extensions.md) ）可以在堆栈上创建，但不能在堆上创建。

下面的示例生成 C3255：

```cpp
// C3255.cpp
// compile with: /clr
using namespace System;
value struct V {
   Object^ o;
};

value struct V2 {
   int i;
};

int main() {
   V* pv = new V;   // C3255
   V2* pv2 = new V2;
   V v2;
}
```
