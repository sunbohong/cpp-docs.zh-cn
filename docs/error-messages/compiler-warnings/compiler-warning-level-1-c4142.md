---
description: 了解详细信息：编译器警告 (等级 1) C4142
title: 编译器警告 (等级 1) C4142
ms.date: 11/04/2016
f1_keywords:
- C4142
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
ms.openlocfilehash: d82403d79310d577cd45fe835cd486719ea0fdc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115724"
---
# <a name="compiler-warning-level-1-c4142"></a>编译器警告 (等级 1) C4142

类型的良性重定义

重定义类型的方式对生成的代码不起作用。

通过检查以下可能的原因进行修复：

- 派生类的成员函数与基类的相应成员函数具有不同的返回类型。

- 使用命令定义的类型 **`typedef`** 将使用不同的语法重新定义。

下面的示例生成 C4142：

```c
// C4142.c
// compile with: /W1
float X2;
X2 = 2.0 + 1.0;   // C4142

int main() {
   float X2;
   X2 = 2.0 + 1.0;   // OK
}
```
