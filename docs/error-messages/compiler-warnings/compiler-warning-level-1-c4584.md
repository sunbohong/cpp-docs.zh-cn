---
description: 了解详细信息：编译器警告 (等级 1) C4584
title: 编译器警告（等级 1）C4584
ms.date: 11/04/2016
f1_keywords:
- C4584
helpviewer_keywords:
- C4584
ms.assetid: ad86582f-cb8c-4d21-8c4c-a6c800059e25
ms.openlocfilehash: 32a6b797f7fb0cf2c1a087999c8172e11686e27b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281621"
---
# <a name="compiler-warning-level-1-c4584"></a>编译器警告（等级 1）C4584

"class1"：基类 "class2" 已是 "a.class3" 的基类

你定义的类继承自两个类，其中一个类继承自另一个类。 例如：

```cpp
// C4584.cpp
// compile with: /W1 /LD
class A {
};

class B : public A {
};

class C : public A, public B { // C4584
};
```

在这种情况下，将在类 C 上发出警告，因为该类继承自类 A 和类 B，后者也从类 A 继承。此警告可作为提醒，你必须完全限定这些基类的成员使用情况，否则将生成编译器错误，因为你引用了哪个类成员。
