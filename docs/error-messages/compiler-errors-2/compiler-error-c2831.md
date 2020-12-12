---
description: 了解更多：编译器错误 C2831
title: 编译器错误 C2831
ms.date: 11/04/2016
f1_keywords:
- C2831
helpviewer_keywords:
- C2831
ms.assetid: c8c04288-0889-4265-a077-17f94cbcdcc9
ms.openlocfilehash: 65fece68763e38de8c5047c66327e0615865fa9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194496"
---
# <a name="compiler-error-c2831"></a>编译器错误 C2831

"operator operator" 不能有默认参数

只有三个运算符可以有默认参数：

- [new](../../cpp/new-operator-cpp.md)

- 赋值 =

- 左括号 (

下面的示例生成 C2831：

```cpp
// C2831.cpp
// compile with: /c
#define BINOP <=
class A {
public:
   int i;
   int operator BINOP(int x = 1) {   // C2831
   // try the following line instead
   // int operator BINOP(int x) {
      return i+x;
   }
};
```
