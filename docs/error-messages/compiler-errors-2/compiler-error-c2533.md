---
description: 了解更多：编译器错误 C2533
title: 编译器错误 C2533
ms.date: 11/04/2016
f1_keywords:
- C2533
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
ms.openlocfilehash: 46f9a18d80bcf75d916a6cf5387dc7145f1f1629
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258117"
---
# <a name="compiler-error-c2533"></a>编译器错误 C2533

“identifier”: 构造函数不能有返回类型

构造函数不能具有返回类型， (甚至不能 **`void`**) 的返回类型。

此错误的常见来源是类定义结尾与第一个构造函数实现之间缺少分号。 编译器会将类视为构造函数返回类型的定义，会生成 C2533。

下面的示例生成 C2533，并演示如何修复此错误：

```cpp
// C2533.cpp
// compile with: /c
class X {
public:
   X();
};

int X::X() {}   // C2533 - constructor return type not allowed
X::X() {}   // OK - fix by using no return type
```
