---
description: 了解更多：编译器错误 C2807
title: 编译器错误 C2807
ms.date: 11/04/2016
f1_keywords:
- C2807
helpviewer_keywords:
- C2807
ms.assetid: bd7a207a-f379-4de6-8ee8-c7cab78b3480
ms.openlocfilehash: 8ce98ee69bf3c41e822a5ecc40dc794b443b6ff0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320618"
---
# <a name="compiler-error-c2807"></a>编译器错误 C2807

后缀 "operator operator" 的第二个形参必须为 "int"

后缀运算符的第二个参数的类型错误。

下面的示例生成 C2807：

```cpp
// C2807.cpp
// compile with: /c
class X {
public:
   X operator++ ( X );   // C2807 nonvoid parameter
   X operator++ ( int );   // OK, int parameter
};
```
