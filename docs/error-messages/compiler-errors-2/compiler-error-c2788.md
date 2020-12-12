---
description: 了解更多：编译器错误 C2788
title: 编译器错误 C2788
ms.date: 11/04/2016
f1_keywords:
- C2788
helpviewer_keywords:
- C2788
ms.assetid: 8688fc5c-e652-43b4-b407-9c488c76f2db
ms.openlocfilehash: 8521df743e6c19f250d0344d4adf2299934887e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297780"
---
# <a name="compiler-error-c2788"></a>编译器错误 C2788

"identifier"：多个与此对象关联的 GUID

[__Uuidof](../../cpp/uuidof-operator.md)运算符使用附加了 GUID 的用户定义类型或此类用户定义类型的对象。 如果参数是具有多个 Guid 的对象，则会发生此错误。

下面的示例生成 C2788：

```cpp
// C2788.cpp
#include <windows.h>
struct __declspec(uuid("00000001-0000-0000-0000-000000000000")) A {};
struct __declspec(uuid("{00000002-0000-0000-0000-000000000000}")) B {};
template <class T, class U> class MyClass {};

typedef MyClass<A,B> MyBadClass;
typedef MyClass<A,A> MyGoodClass;

int main() {
   __uuidof(MyBadClass);    // C2788
   // try the following line instead
   __uuidof(MyGoodClass);
}
```
