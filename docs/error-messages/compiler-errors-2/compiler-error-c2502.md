---
description: 了解更多：编译器错误 C2502
title: 编译器错误 C2502
ms.date: 11/04/2016
f1_keywords:
- C2502
helpviewer_keywords:
- C2502
ms.assetid: affa0b86-15fc-4e17-b7f2-6aad4a3771c4
ms.openlocfilehash: 6ee501a5fa3601ef5e4b97d4be5a8e59463ce797
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275927"
---
# <a name="compiler-error-c2502"></a>编译器错误 C2502

"identifier"：基类上的访问修饰符太多

基类具有多个访问修饰符。 只允许使用一个访问修饰符 (**`public`** 、 **`private`** 或 **`protected`**) 。

下面的示例生成 C2502：

```cpp
// C2502.cpp
// compile with: /c
class A { };
class B { };
class C : private public A { };   // C2502

// OK
class D : private A {};
class E : public A, private B {};
```
