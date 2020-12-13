---
description: 了解详细信息：编译器警告 (等级 1) C4602
title: 编译器警告（等级 1）C4602
ms.date: 11/04/2016
f1_keywords:
- C4602
helpviewer_keywords:
- C4602
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
ms.openlocfilehash: 7027d97c1e47fd03211a8243aa22c2aad34181c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341758"
---
# <a name="compiler-warning-level-1-c4602"></a>编译器警告（等级 1）C4602

\#pragma pop_macro： "宏名" 没有此标识符前面的 #pragma push_macro

如果你对于特定的宏使用 [pop_macro](../../preprocessor/pop-macro.md) ，你首先必须将宏的名称传递到 [push_macro](../../preprocessor/push-macro.md)。 例如，以下示例生成 C4602：

```cpp
// C4602.cpp
// compile with: /W1
int main()
{
   #pragma pop_macro("x")   // C4602 x is not on the stack
}
```
