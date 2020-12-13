---
description: 详细了解：编译器警告 (级别 4) C4740
title: 编译器警告（等级 4）C4740
ms.date: 11/04/2016
f1_keywords:
- C4740
helpviewer_keywords:
- C4740
ms.assetid: 85528969-966a-44b4-8a2f-971704c64477
ms.openlocfilehash: 31c25660177931e468681f3e563a9885ca1faa01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330528"
---
# <a name="compiler-warning-level-4-c4740"></a>编译器警告（等级 4）C4740

流入或流出内联 asm 代码取消全局优化

跳转到或跳出 **`asm`** 块时，将对该函数禁用全局优化。

下面的示例生成 C4740：

```cpp
// C4740.cpp
// compile with: /O2 /W4
// processor: x86
int main() {
   __asm jmp tester
   tester:;
}
```
