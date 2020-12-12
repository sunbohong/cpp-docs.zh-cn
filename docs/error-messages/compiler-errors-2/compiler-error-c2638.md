---
description: 了解更多：编译器错误 C2638
title: 编译器错误 C2638
ms.date: 11/04/2016
f1_keywords:
- C2638
helpviewer_keywords:
- C2638
ms.assetid: 9d4275e8-406d-455e-afee-3a37799230e0
ms.openlocfilehash: 82921314b8861239e1686c95f8a0c3bc4eb41082
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272443"
---
# <a name="compiler-error-c2638"></a>编译器错误 C2638

"identifier"： __based 修饰符在指向成员的指针上非法

**`__based`** 修饰符不能用于指向成员的指针。

下面的示例生成 C2638：

```cpp
// C2638.cpp
void *a;

class C {
public:
   int i;
   int j;
   int func();
};
int __based (a) C::* cpi = &C::i;  // C2638
int (__based (a) C::* cpf)() = &C::func; // c2638
```
