---
description: 了解详细信息：编译器警告 (等级 1) C4552
title: 编译器警告（等级 1）C4552
ms.date: 11/04/2016
f1_keywords:
- C4552
helpviewer_keywords:
- C4552
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
ms.openlocfilehash: 52cea1aac8b46fc5c1958bd917f6ab910ef326c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265917"
---
# <a name="compiler-warning-level-1-c4552"></a>编译器警告（等级 1）C4552

"operator"：运算符不起任何作用;应有副作用的运算符

如果表达式语句的运算符没有副作用作为表达式的顶部，则这可能是错误的。

若要覆盖此警告，请将表达式放在括号中。

下面的示例生成 C4552：

```cpp
// C4552.cpp
// compile with: /W1
int main() {
   int i, j;
   i + j;   // C4552
   // try the following line instead
   // (i + j);
}
```
