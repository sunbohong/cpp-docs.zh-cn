---
description: 了解更多：编译器错误 C2637
title: 编译器错误 C2637
ms.date: 11/04/2016
f1_keywords:
- C2637
helpviewer_keywords:
- C2637
ms.assetid: 58d94447-eb96-4d8f-a690-dd78d322462e
ms.openlocfilehash: 1f42a732d5dfa3f7c94e0cc755bd1db00c8ff56b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208718"
---
# <a name="compiler-error-c2637"></a>编译器错误 C2637

"identifier"：不能修改指向数据成员的指针

指向数据成员的指针不能具有调用约定。 若要解决此问题，请删除调用约定或声明指向成员函数的指针。

下面的示例生成 C2637：

```cpp
// C2637.cpp
// compile with: /c
struct S {};
int __stdcall S::*pms1;   // C2637

// OK
int S::*pms2;
int (__stdcall S::*pms3)(...);
```
