---
description: 了解更多：编译器错误 C3149
title: 编译器错误 C3149
ms.date: 11/04/2016
f1_keywords:
- C3149
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
ms.openlocfilehash: 596a8d2728e7598a737da4aa5a1650df669db969
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322085"
---
# <a name="compiler-error-c3149"></a>编译器错误 C3149

"type"：不能在没有顶级 "char" 的情况下使用此类型

未正确指定声明。

例如，你可能在全局范围内定义了 CLR 类型，并尝试在定义中创建类型为的变量。 由于不允许使用 CLR 类型的全局变量，编译器将生成 C3149。

若要解决此错误，请在函数或类型定义中声明 CLR 类型的变量。

下面的示例生成 C3149：

```cpp
// C3149.cpp
// compile with: /clr
using namespace System;
int main() {
   // declare an array of value types
   array< Int32 ^> IntArray;   // C3149
   array< Int32>^ IntArray2;   // OK
}
```

下面的示例生成 C3149：

```cpp
// C3149b.cpp
// compile with: /clr /c
delegate int MyDelegate(const int, int);
void Test1(MyDelegate m) {}   // C3149
void Test2(MyDelegate ^ m) {}   // OK
```
