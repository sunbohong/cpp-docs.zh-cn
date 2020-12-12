---
description: 详细了解：编译器警告 (级别 4) C4408
title: 编译器警告（等级 4）C4408
ms.date: 11/04/2016
f1_keywords:
- C4408
helpviewer_keywords:
- C4408
ms.assetid: 8488a186-ed1d-425c-aaeb-c72472c1da68
ms.openlocfilehash: 94764cd23c8bf4af757afa7bd8a084f61c5f24a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251474"
---
# <a name="compiler-warning-level-4-c4408"></a>编译器警告（等级 4）C4408

anonymousstruct 或 union 未声明任何数据成员

匿名结构或联合必须具有至少一个数据成员。

以下示例生成 C4408：

```cpp
// C4408.cpp
// compile with: /W4 /LD
static union
{
   // int i;
};
// a named union can have no data members
// } MyUnion;
```
