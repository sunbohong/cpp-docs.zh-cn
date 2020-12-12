---
description: 了解更多：编译器错误 C2213
title: 编译器错误 C2213
ms.date: 11/04/2016
f1_keywords:
- C2213
helpviewer_keywords:
- C2213
ms.assetid: ff012278-7f3b-4d49-aaed-2349756f6225
ms.openlocfilehash: aa9274f77c2416af286c306f2e6302b5f416a24b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245585"
---
# <a name="compiler-error-c2213"></a>编译器错误 C2213

"修饰符"：非法的参数 __based

修改参数 **`__based`** 无效。

下面的示例生成 C2213：

```cpp
// C2213.cpp
// compile with: /c
int i;
int *j;
char __based(i) *p;   // C2213
char __based(j) *p2;   // OK
```
