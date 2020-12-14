---
description: 详细了解：编译器警告 (级别 4) C4254
title: 编译器警告（等级 4）C4254
ms.date: 11/04/2016
f1_keywords:
- c4254
helpviewer_keywords:
- C4254
ms.assetid: c7dcef24-d535-4c98-bb41-fc3d2b88fd11
ms.openlocfilehash: 112a8c4af016b15f6a5ec4c6e138381a8ee32405
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294699"
---
# <a name="compiler-warning-level-4-c4254"></a>编译器警告（等级 4）C4254

"operator"：从 "type1" 转换到 "type2"，可能丢失数据

将较大的位域分配给较小的位域。 可能会丢失数据。

默认情况下，此警告处于关闭状态。 请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 了解详细信息。

下面的示例生成 C4254：

```cpp
// C4254.cpp
// compile with: /W4
#pragma warning(default: 4254)

struct X {
   int a : 20;
   int b : 12;
};

int main() {
   X *x = new X();
   x->b = 10;
   x->a = 4;
   x->a = x->b;    // OK
   x->b = x->a;    // C4254
};
```
