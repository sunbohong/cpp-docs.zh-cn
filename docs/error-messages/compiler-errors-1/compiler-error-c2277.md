---
description: 了解更多：编译器错误 C2277
title: 编译器错误 C2277
ms.date: 11/04/2016
f1_keywords:
- C2277
helpviewer_keywords:
- C2277
ms.assetid: 15a83b07-8731-4524-810b-267f65a7844f
ms.openlocfilehash: e5113587b22373eae4a197b5913430659447810a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344427"
---
# <a name="compiler-error-c2277"></a>编译器错误 C2277

"identifier"：无法获取此成员函数的地址

不能采用成员函数的地址。

下面的示例生成 C2277：

```cpp
// C2277.cpp
class A {
public:
   A();
};
(*pctor)() = &A::A;   // C2277
```
