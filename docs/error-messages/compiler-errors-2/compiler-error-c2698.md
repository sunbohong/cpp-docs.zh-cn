---
description: 了解更多：编译器错误 C2698
title: 编译器错误 C2698
ms.date: 11/04/2016
f1_keywords:
- C2698
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
ms.openlocfilehash: a787c43e7a885734f4c6a2d76aa16d51e19615c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326625"
---
# <a name="compiler-error-c2698"></a>编译器错误 C2698

"声明 1" 的 using 声明不能与 "声明 2" 的现有 using 声明共存

为数据成员 [使用了声明](../../cpp/using-declaration.md) 后，不允许使用同一范围内的任何 using 声明，因为只能重载函数。

下面的示例生成 C2698：

```cpp
// C2698.cpp
struct A {
   int x;
};

struct B {
   int x;
};

struct C : A, B {
   using A::x;
   using B::x;   // C2698
}
```
