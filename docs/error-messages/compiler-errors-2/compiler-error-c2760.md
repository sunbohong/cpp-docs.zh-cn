---
description: 了解更多：编译器错误 C2760
title: 编译器错误 C2760
ms.date: 11/04/2016
f1_keywords:
- C2760
helpviewer_keywords:
- C2760
ms.assetid: 585757fd-d519-43f3-94e5-50316ac8b90b
ms.openlocfilehash: bba26b68a2e4c98cf478098b2e44e82962afd9f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336164"
---
# <a name="compiler-error-c2760"></a>编译器错误 C2760

> 语法错误：应为 "*name1*" 而不是 "*name2*"

## <a name="remarks"></a>备注

有多种方法可导致此错误。 通常，它是由编译器无法识别的令牌序列引起的。

## <a name="example"></a>示例

在此示例中，转换运算符与无效运算符一起使用。

```cpp
// C2760.cpp
class B {};
class D : public B {};

void f(B* pb) {
    D* pd1 = static_cast<D*>(pb);
    D* pd2 = static_cast<D*>=(pb);  // C2760
    D* pd3 = static_cast<D*=(pb);   // C2760
}
```
