---
description: 了解更多：编译器错误 C2652
title: 编译器错误 C2652
ms.date: 11/04/2016
f1_keywords:
- C2652
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
ms.openlocfilehash: 6d0f85a089c527ce299e007ce04d96ac68daaf56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286171"
---
# <a name="compiler-error-c2652"></a>编译器错误 C2652

"identifier"：非法的复制构造函数：第一个参数不能是 "identifier"

复制构造函数中的第一个参数的类型与定义它的类、结构或联合的类型相同。 第一个参数可以是对类型的引用，但不能是类型本身。

下面的示例生成 C2651：

```cpp
// C2652.cpp
// compile with: /c
class A {
   A( A );   // C2652 takes an A
};
class B {
   B( B& );   // OK, reference to B
};
```
