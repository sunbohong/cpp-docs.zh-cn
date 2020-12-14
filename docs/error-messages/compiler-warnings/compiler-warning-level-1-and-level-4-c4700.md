---
description: 了解详细信息：编译器警告 (等级1和等级 4) C4700
title: 编译器警告（等级 1 和等级 4）C4700
ms.date: 02/21/2018
f1_keywords:
- C4700
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
ms.openlocfilehash: 7ba19bdd6d8e25e095f796adc8cdb60b5cc8d325
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241594"
---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>编译器警告（等级 1 和等级 4）C4700

> 使用了未初始化的局部变量 "*name*"

局部变量 *名称* 已被 *使用*，即在分配值之前从中读取。 在 C 和 c + + 中，默认情况下不初始化局部变量。 未初始化的变量可以包含任何值，其使用会导致未定义的行为。 警告 C4700 几乎总是指示一个 bug，该 bug 可能导致程序中出现不可预测的结果或故障。

若要解决此问题，可以在声明本地变量时对其进行初始化，或在使用之前为它们赋值。 函数可用于初始化作为引用参数传递的变量，或将其地址作为指针参数传递时使用。

## <a name="example"></a>示例

此示例在初始化变量 t、u 和 v 之前，生成 C4700，并显示可能产生的垃圾值的种类。 变量 x、y 和 z 不会导致此警告，因为它们会在使用之前进行初始化：

```cpp
// c4700.cpp
// compile by using: cl /EHsc /W4 c4700.cpp
#include <iostream>

// function takes an int reference to initialize
void initialize(int& i)
{
    i = 21;
}

int main()
{
    int s, t, u, v;   // Danger, uninitialized variables

    s = t + u + v;    // C4700: t, u, v used before initialization
    std::cout << "Value in s: " << s << std::endl;

    int w, x;         // Danger, uninitialized variables
    initialize(x);    // fix: call function to init x before use
    int y{10};        // fix: initialize y, z when declared
    int z{11};        // This C++11 syntax is recommended over int z = 11;

    w = x + y + z;    // Okay, all values initialized before use
    std::cout << "Value in w: " << w << std::endl;
}
```

此代码运行时，t、u 和 v 处于未初始化状态，并且 s 的输出是不可预知的：

```Output
Value in s: 37816963
Value in w: 42
```
