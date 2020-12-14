---
description: 了解详细信息：编译器警告 (等级 1) C4405
title: 编译器警告（等级 1）C4405
ms.date: 11/04/2016
f1_keywords:
- C4405
helpviewer_keywords:
- C4405
ms.assetid: 155c64d6-58ae-4455-b61f-ccd711c5da96
ms.openlocfilehash: 53b70ea7d3e55ed23f398c912daeb69827715a58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311079"
---
# <a name="compiler-warning-level-1-c4405"></a>编译器警告（等级 1）C4405

"identifier"：标识符是保留字

为内联程序集保留的字用作变量名。 这可能会导致不可预知的结果。 若要修复此警告，请避免用为内联程序集保留的字命名变量。 下面的示例生成 C4405：

```cpp
// C4405.cpp
// compile with: /W1
// processor: x86
void func1() {
   int mov = 0, i = 0;
   _asm {
      mov mov, 0;   // C4405
      // instead, try ..
      // mov i, 0;
   }
}

int main() {
}
```
