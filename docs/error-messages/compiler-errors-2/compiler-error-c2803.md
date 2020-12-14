---
description: 了解更多：编译器错误 C2803
title: 编译器错误 C2803
ms.date: 11/04/2016
f1_keywords:
- C2803
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
ms.openlocfilehash: 405c14d05bad4c505d847b8ab2648a7ace3b9a4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297429"
---
# <a name="compiler-error-c2803"></a>编译器错误 C2803

"operator operator" 必须至少有一个类类型的形参

重载运算符缺少类类型的参数。

你需要通过引用传递至少一个参数 (不使用指针，但引用) 或通过值来编写 "a < b" (a 和 b 的类型为类 A) 。

如果这两个参数都是指针，则它将是指针地址的纯粹比较，并且不会使用用户定义的转换。

下面的示例生成 C2803：

```cpp
// C2803.cpp
// compile with: /c
class A{};
bool operator< (const A *left, const A *right);   // C2803
// try the following line instead
// bool operator< (const A& left, const A& right);
```
