---
description: 详细了解：编译器警告 (级别 4) C4130
title: 编译器警告（等级 4）C4130
ms.date: 11/04/2016
f1_keywords:
- C4130
helpviewer_keywords:
- C4130
ms.assetid: 45e4c7b2-6b51-41c7-ba5e-941aa5c7d3dc
ms.openlocfilehash: e7096f471405b0b22bcb0a825dd9ccd0de4e3510
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261809"
---
# <a name="compiler-warning-level-4-c4130"></a>编译器警告（等级 4）C4130

“operator”：字符串常量地址的逻辑操作

使用具有字符串文本地址的运算符会产生意外的代码。

下面的示例生成 C4130：

```cpp
// C4130.cpp
// compile with: /W4
int main()
{
   char *pc;
   pc = "Hello";
   if (pc == "Hello") // C4130
   {
   }
}
```

语句会将 **`if`** 指针中存储的值 `pc` 与字符串 "Hello" 的地址进行比较，每次在代码中出现该字符串时，都将单独分配该地址。 **`if`** 语句不会将所指向的字符串 `pc` 与字符串 "Hello" 进行比较。

若要比较字符串，请使用 `strcmp` 函数。
