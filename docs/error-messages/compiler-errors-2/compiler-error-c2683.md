---
description: 了解更多：编译器错误 C2683
title: 编译器错误 C2683
ms.date: 11/04/2016
f1_keywords:
- C2683
helpviewer_keywords:
- C2683
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
ms.openlocfilehash: 9cb13204163370ea529c88cc5648a25a4e520370
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220768"
---
# <a name="compiler-error-c2683"></a>编译器错误 C2683

"cast"： "type" 不是多态类型

不能使用 [dynamic_cast](../../cpp/dynamic-cast-operator.md) 从非多态类转换 (不具有虚函数) 的类。

您可以使用 [static_cast](../../cpp/static-cast-operator.md) 来执行非多态类型的转换。 但是，不 **`static_cast`** 执行运行时检查。

下面的示例生成 C2683：

```cpp
// C2683.cpp
// compile with: /c
class B { };
class D : public B { };

void f(B* pb) {
   D* pd1 = dynamic_cast<D*>(pb);  // C2683
   D* pd1 = static_cast<D*>(pb);   // OK
}
```
