---
description: 详细了解：编译器警告 (级别 4) C4208
title: 编译器警告（等级 4）C4208
ms.date: 11/04/2016
f1_keywords:
- C4208
helpviewer_keywords:
- C4208
ms.assetid: 5cb0a36e-3fb5-422f-a5f9-e40b70776c27
ms.openlocfilehash: a99e9435fcdbfb65248fb38883a8f3395ef4db14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314771"
---
# <a name="compiler-warning-level-4-c4208"></a>编译器警告（等级 4）C4208

使用了非标准扩展： delete [exp]-计算但忽略 exp

使用 Microsoft extensions (/Ze) ，可以使用包含 [delete 运算符](../../cpp/delete-operator-cpp.md)的括号内的值删除数组。 值被忽略。

```cpp
// C4208.cpp
// compile with: /W4
int main()
{
   int * MyArray = new int[18];
   delete [18] MyArray;      // C4208
   MyArray = new int[18];
   delete [] MyArray;        // ok
}
```

此类值在 ANSI 兼容性 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 下无效。
