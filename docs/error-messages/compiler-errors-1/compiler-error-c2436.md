---
description: 了解更多：编译器错误 C2436
title: 编译器错误 C2436
ms.date: 11/04/2016
f1_keywords:
- C2436
helpviewer_keywords:
- C2436
ms.assetid: ca4cc813-bc1d-4c0a-9a2c-3a5fe673d084
ms.openlocfilehash: 3858146d48006c1129f6dca1992e229603b70a79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189907"
---
# <a name="compiler-error-c2436"></a>编译器错误 C2436

"identifier"：构造函数初始值设定项列表中的成员函数或嵌套类

构造函数初始值设定项列表中的成员函数或局部类无法初始化。

下面的示例生成 C2436：

```cpp
// C2436.cpp
struct S{
   int f();
   struct Inner{
      int i;
   };
   S():f(10), Inner(0){}   // C2436
};
```
