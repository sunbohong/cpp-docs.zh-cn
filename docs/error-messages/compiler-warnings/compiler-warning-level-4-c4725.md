---
description: 详细了解：编译器警告 (级别 4) C4725
title: 编译器警告（等级 4）C4725
ms.date: 11/04/2016
f1_keywords:
- C4725
helpviewer_keywords:
- C4725
ms.assetid: effa0335-71c3-4b3b-8618-da4b9b46a95d
ms.openlocfilehash: 636f6fb18c3ffb18a2f4b845a4584324cf59d72a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330555"
---
# <a name="compiler-warning-level-4-c4725"></a>编译器警告（等级 4）C4725

在一些 Pentium 中，指令可能不准确

你的代码包含某种内联程序集指令，其可能在某些 Pentium 微处理器上不会产生准确结果。

以下示例生成 C4725：

```cpp
// C4725.cpp
// compile with: /W4
// processor: x86
double m32fp = 2.0003e-17;

void f() {
   __asm
   {
      FDIV m32fp   // C4725
   }
}

int main() {
}
```
