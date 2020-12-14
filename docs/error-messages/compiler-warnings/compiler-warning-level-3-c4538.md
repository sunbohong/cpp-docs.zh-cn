---
description: 详细了解：编译器警告 (等级 3) C4538
title: 编译器警告（等级 3）C4538
ms.date: 11/04/2016
f1_keywords:
- C4538
helpviewer_keywords:
- C4538
ms.assetid: 747e3d51-b6d0-41c1-a726-7af3253b59d7
ms.openlocfilehash: 4f5d6ee8b6144db4fad519f1484d00fe325591a2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257844"
---
# <a name="compiler-warning-level-3-c4538"></a>编译器警告（等级 3）C4538

"type"：不支持此类型上的 const/volatile 限定符

限定符关键字未正确应用于数组。 有关详细信息，请参阅 [数组](../../extensions/arrays-cpp-component-extensions.md)。

下面的示例生成 C4538：

```cpp
// C4538.cpp
// compile with: /clr /W3 /LD
const array<int> ^f1();   // C4538
array<const int> ^f2();   // OK
```
