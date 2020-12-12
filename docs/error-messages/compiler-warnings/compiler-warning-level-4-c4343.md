---
description: 详细了解：编译器警告 (级别 4) C4343
title: 编译器警告（等级 4）C4343
ms.date: 11/04/2016
f1_keywords:
- C4343
helpviewer_keywords:
- C4343
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
ms.openlocfilehash: 906dee40eb0e9ef55c67657e93f42a6e2279a9d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294491"
---
# <a name="compiler-warning-level-4-c4343"></a>编译器警告（等级 4）C4343

\#pragma optimize ( "g"，off) 重写/Og 选项

此警告（仅在 Itanium 处理器系列 (IPF) 编译器中有效）报告 pragma [optimize](../../preprocessor/optimize.md) 重写 [/Og](../../build/reference/og-global-optimizations.md) 编译器选项。

下面的示例生成 C4343：

```cpp
// C4343.cpp
// compile with: /Og /W4 /LD
// processor: IPF
#pragma optimize ("g", off)   // C4343
```
