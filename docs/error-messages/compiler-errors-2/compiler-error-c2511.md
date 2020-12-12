---
description: 了解更多：编译器错误 C2511
title: 编译器错误 C2511
ms.date: 11/04/2016
f1_keywords:
- C2511
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
ms.openlocfilehash: 846173cc887fd09b564d18e063820bc0e0d5b184
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212917"
---
# <a name="compiler-error-c2511"></a>编译器错误 C2511

"identifier"：在 "class" 中找不到重载成员函数

未用指定参数声明函数的任何版本。  可能的原因：

1. 传递给函数的参数错误。

1. 传递的参数的顺序不正确。

1. 参数名称的拼写不正确。

下面的示例生成 C2511：

```cpp
// C2511.cpp
// compile with: /c
class C {
   int c_2;
   int Func(char *, char *);
};

int C::Func(char *, char *, int i) {   // C2511
// try the following line instead
// int C::Func(char *, char *) {
   return 0;
}
```
