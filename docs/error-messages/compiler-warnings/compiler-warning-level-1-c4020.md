---
description: 了解详细信息：编译器警告 (等级 1) C4020
title: 编译器警告 (等级 1) C4020
ms.date: 11/04/2016
f1_keywords:
- C4020
helpviewer_keywords:
- C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
ms.openlocfilehash: 454bab1eb8a3d1da6d0fe8bf508de8c466d22001
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241568"
---
# <a name="compiler-warning-level-1-c4020"></a>编译器警告 (等级 1) C4020

"function"：实参太多

函数调用中的实参数量超过函数原型或定义中的形参数量。 编译器会根据函数的调用约定传递额外的实际参数。

下面的示例生成 C4020：

```c
// C4020.c
// compile with: /W1 /c
void f(int);
int main() {
   f(1,2);   // C4020
}
```

可能的解决方法：

```c
// C4020b.c
// compile with: /c
void f(int);
int main() {
   f(1);
}
```
