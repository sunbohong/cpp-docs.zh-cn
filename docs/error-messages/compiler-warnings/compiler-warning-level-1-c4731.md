---
description: 了解详细信息：编译器警告 (等级 1) C4731
title: 编译器警告（等级 1）C4731
ms.date: 11/04/2016
f1_keywords:
- C4731
helpviewer_keywords:
- C4731
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
ms.openlocfilehash: d2041936d7d3c4b7189f57d57ffb1c9f226ea933
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228646"
---
# <a name="compiler-warning-level-1-c4731"></a>编译器警告（等级 1）C4731

"指针"：框架指针寄存器 "register" 由内联程序集代码修改

修改了帧指针寄存器。 你必须在内联程序集块或框架变量 (本地或参数中保存和还原注册，具体取决于已修改的) ，或你的代码可能无法正常工作。

下面的示例生成 C4731：

```cpp
// C4731.cpp
// compile with: /W1 /LD
// processor: x86
// C4731 expected
void bad(int p) {
   __asm
   {
      mov ebp, 1
   }

   if (p == 1)
   {
      // ...
   }
}
```

EBP 是不允许)  (FPO 的帧指针，并且正在修改它。 `p`以后引用时，相对于引用它 `EBP` 。 但已被 `EBP` 代码覆盖，所以程序将无法正常工作，甚至可能出现故障。
