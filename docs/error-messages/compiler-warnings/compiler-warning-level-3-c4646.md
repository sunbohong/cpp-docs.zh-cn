---
description: 详细了解：编译器警告 (等级 3) C4646
title: 编译器警告（等级 3）C4646
ms.date: 11/04/2016
f1_keywords:
- C4646
helpviewer_keywords:
- C4646
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
ms.openlocfilehash: 045c5d4557a50824235833528f8b46ff77b683e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301823"
---
# <a name="compiler-warning-level-3-c4646"></a>编译器警告（等级 3）C4646

用 __declspec(noreturn) 声明的函数有非 void 返回类型

标记有 [noreturn](../../cpp/noreturn.md) **`__declspec`** 修饰符的函数应具有 [void](../../cpp/void-cpp.md) 返回类型。

下面的示例生成 C4646：

```cpp
// C4646.cpp
// compile with: /W3 /WX
int __declspec(noreturn) TestFunction()
{   // C4646  make return type void
}
```
