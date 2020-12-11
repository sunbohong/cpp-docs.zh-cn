---
description: 详细了解：编译器警告 (等级 3) C4390
title: 编译器警告（等级 3）C4390
ms.date: 11/04/2016
f1_keywords:
- C4390
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
ms.openlocfilehash: 8067d4beae44e098085122968a227f6ff8bc8b4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160436"
---
# <a name="compiler-warning-level-3-c4390"></a>编译器警告（等级 3）C4390

";"：找到空的受控语句;这是不是吗？

在不包含指令的控制语句之后发现了分号。

如果由于宏而获得 C4390，则应使用 [警告](../../preprocessor/warning.md) 杂注禁用包含宏的模块中的 C4390。

下面的示例生成 C4390：

```cpp
// C4390.cpp
// compile with: /W3
int main() {
   int i = 0;
   if (i);   // C4390
      i++;
}
```
