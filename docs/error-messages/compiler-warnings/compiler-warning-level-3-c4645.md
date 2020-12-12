---
description: 详细了解：编译器警告 (等级 3) C4645
title: 编译器警告（等级 3）C4645
ms.date: 11/04/2016
f1_keywords:
- C4645
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
ms.openlocfilehash: 1002abfa66eddbf4891f9d57af96bf0b949cd483
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305294"
---
# <a name="compiler-warning-level-3-c4645"></a>编译器警告（等级 3）C4645

用 __declspec(noreturn) 声明的函数有返回语句

在标记有 [noreturn](../../cpp/noreturn.md)修饰符的函数中发现了 [返回](../../cpp/program-termination.md)语句 **`__declspec`** 。 **`return`** 语句已被忽略。

下面的示例生成 C4645：

```cpp
// C4645.cpp
// compile with:  /W3
void __declspec(noreturn) func() {
   return;   // C4645, delete this line to resolve
}

int main() {
}
```
