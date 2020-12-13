---
description: 了解更多：编译器错误 C2184
title: 编译器错误 C2184
ms.date: 11/04/2016
f1_keywords:
- C2184
helpviewer_keywords:
- C2184
ms.assetid: 80fc8bff-7d76-4bde-94d2-01d84bb6824a
ms.openlocfilehash: 26513ff4162023398336eae3396e7be6abb8f8a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335149"
---
# <a name="compiler-error-c2184"></a>编译器错误 C2184

“type”：对 __except 表达式而言为非法类型，必须为整型

[__except](../../c-language/try-except-statement-c.md) 语句中使用了某个类型，但不允许使用该类型。

下面的示例生成 C2184：

```cpp
// C2184.cpp
void f() {
   int * p;
   __try{}
   __except(p){};   // C2184
}
```

可能的解决方法：

```cpp
// C2184b.cpp
// compile with: /c
void f() {
   int i = 0;
   __try{}
   __except(i){};
}
```
