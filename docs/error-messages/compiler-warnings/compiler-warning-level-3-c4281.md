---
description: 详细了解：编译器警告 (等级 3) C4281
title: 编译器警告（等级 3）C4281
ms.date: 11/04/2016
f1_keywords:
- C4281
helpviewer_keywords:
- C4281
ms.assetid: a9771261-5725-4fc6-87b6-16cf92113a25
ms.openlocfilehash: ad62244fb851e9aed93cb2c3f48282b77f0cf411
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344115"
---
# <a name="compiler-warning-level-3-c4281"></a>编译器警告（等级 3）C4281

"operator->" 通过类型 "type" 发生递归

你的代码允许 **操作员 >** 调用其自身。

下面的示例生成 C4281：

```cpp
// C4281.cpp
// compile with: /W3 /WX
struct A;
struct B;
struct C;

struct A
{
   int z;
   B& operator->();
};

struct B
{
   C& operator->();
};

struct C
{
   A& operator->();
};

void f(A p)
{
   int i = p->z; // C4281
}
```
