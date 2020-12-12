---
description: 了解更多：编译器错误 C2073
title: 编译器错误 C2073
ms.date: 11/04/2016
f1_keywords:
- C2073
helpviewer_keywords:
- C2073
ms.assetid: 57908234-be7a-4ce9-b0a7-8b1ad621865e
ms.openlocfilehash: 791f07040b0a0dd70d2cb0aa8373eb6c342c5b97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209160"
---
# <a name="compiler-error-c2073"></a>编译器错误 C2073

"identifier"：部分初始化数组的元素必须有默认构造函数

为用户定义的类型或常量的数组指定了太少的初始值设定项。 如果没有为数组成员指定显式初始值设定项及其相应的构造函数，则必须提供默认构造函数。

下面的示例生成 C2073：

```cpp
// C2073.cpp
class A {
public:
   A( int );   // constructor for ints only
};
A a[3] = { A(1), A(2) };   // C2073, no default constructor
```

```cpp
// C2073b.cpp
// compile with: /c
class B {
public:
   B();   // default constructor declared
   B( int );
};
B b[3] = { B(1), B(2) };   // OK
```
