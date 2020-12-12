---
description: 了解更多：编译器错误 C2969
title: 编译器错误 C2969
ms.date: 11/04/2016
f1_keywords:
- C2969
helpviewer_keywords:
- C2969
ms.assetid: e4ea3d66-b937-4b2c-b42a-96e03fb11579
ms.openlocfilehash: d0b52e6033338adc249cc9c7181cbb5dc25f7f8b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210395"
---
# <a name="compiler-error-c2969"></a>编译器错误 C2969

语法错误: “symbol”: 成员函数定义应以“}”结尾

模板成员函数定义具有不匹配的右大括号。

以下示例生成 C2969：

```cpp
// C2969.cpp
// compile with: /c
class A {
   int i;
public:
   A(int i) {}
};

A anA(1);

class B {
   A a;
   B() : a(anA);   // C2969
   // try the following line instead
   // B() : a(anA) {}
};
```
