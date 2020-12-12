---
description: 了解更多：编译器错误 C2507
title: 编译器错误 C2507
ms.date: 11/04/2016
f1_keywords:
- C2507
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
ms.openlocfilehash: b2043f01cea9a64ace11fbdaa8d905fd892cc99c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212969"
---
# <a name="compiler-error-c2507"></a>编译器错误 C2507

"identifier"：基类上的虚拟修饰符太多

一个类或结构被声明为多次 **`virtual`** 。 **`virtual`** 对于基类列表中的每个类，只能显示一个修饰符。

下面的示例生成 C2507：

```cpp
// C2507.cpp
// compile with: /c
class A {};
class B : virtual virtual public A {};   // C2507
class C : virtual public A {};   // OK
```
