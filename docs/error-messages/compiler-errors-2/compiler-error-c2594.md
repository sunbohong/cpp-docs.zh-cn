---
description: 了解更多：编译器错误 C2594
title: 编译器错误 C2594
ms.date: 11/04/2016
f1_keywords:
- C2594
helpviewer_keywords:
- C2594
ms.assetid: 68cd708f-266e-44b0-a211-3e3ab63b11bf
ms.openlocfilehash: 972fb58624a7f2ba185c34f2e58fd9f2dc15217d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120147"
---
# <a name="compiler-error-c2594"></a>编译器错误 C2594

"operator"：从 "type1" 到 "type2" 的转换不明确

从 *type1* 到 *type2* 的转换不是任何其他的直接转换。 建议将两个可能的解决方案从 *type1* 转换为 *type2*。 第一种方法是定义从 *type1* 到 *type2* 的直接转换，第二种方法是指定从 *type1* 到 *type2* 的转换序列。

下面的示例生成 C2594。 建议的错误解决方法是转换序列：

```cpp
// C2594.cpp
// compile with: /c
struct A{};
struct I1 : A {};
struct I2 : A {};
struct D : I1, I2 {};

A *f (D *p) {
   return (A*) (p);    // C2594

// try the following line instead
// return static_cast<A *>(static_cast<I1 *>(p));
}
```
