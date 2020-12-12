---
description: 了解更多：编译器错误 C2593
title: 编译器错误 C2593
ms.date: 11/04/2016
f1_keywords:
- C2593
helpviewer_keywords:
- C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
ms.openlocfilehash: 849cd79b1d469d957cf1bde499ce66bd54a64074
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120160"
---
# <a name="compiler-error-c2593"></a>编译器错误 C2593

"operator identifier" 不明确

为重载运算符定义了多个可能的运算符。

如果对一个或多个实际参数使用显式强制转换，则可能会修复此错误。

下面的示例生成 C2593：

```cpp
// C2593.cpp
struct A {};
struct B : A {};
struct X {};
struct D : B, X {};
void operator+( X, X );
void operator+( A, B );
D d;

int main() {
   d +  d;         // C2593, D has an A, B, and X
   (X)d + (X)d;    // OK, uses operator+( X, X )
}
```

使用对象序列化浮点变量可能导致此错误 `CArchive` 。 编译器将运算符标识 `<<` 为不明确。 可以序列化的唯一基元 c + + 类型 `CArchive` 为固定大小的类型 `BYTE` ：、 `WORD` `DWORD` 和 `LONG` 。 所有整数类型都必须强制转换为这些类型之一以进行序列化。 必须使用成员函数存档浮点类型 `CArchive::Write()` 。

下面的示例演示如何将浮点变量 (`f`) 存档 `ar` ：

```
ar.Write(&f, sizeof( float ));
```
