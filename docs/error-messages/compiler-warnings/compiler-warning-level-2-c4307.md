---
description: 详细了解：编译器警告 (等级 2) C4307
title: 编译器警告（等级 2）C4307
ms.date: 11/04/2016
f1_keywords:
- C4307
helpviewer_keywords:
- C4307
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
ms.openlocfilehash: 5de4279d430f3275d61c6dca3d9db161c4ac5f11
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339203"
---
# <a name="compiler-warning-level-2-c4307"></a>编译器警告（等级 2）C4307

"operator"：整型常量溢出

运算符用于导致整数常量溢出为其分配的空间的表达式。 可能需要对常数使用较大的类型。 **`signed int`** 保留比更小的值， **`unsigned int`** 因为 **`signed int`** 使用一位表示符号。

下面的示例生成 C4307：

```cpp
// C4307.cpp
// compile with: /W2
int i = 2000000000 + 2000000000;   // C4307
int j = (unsigned)2000000000 + 2000000000;   // OK

int main()
{
}
```
