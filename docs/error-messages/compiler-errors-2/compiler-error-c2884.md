---
description: 了解更多：编译器错误 C2884
title: 编译器错误 C2884
ms.date: 11/04/2016
f1_keywords:
- C2884
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
ms.openlocfilehash: 008c72ba24bdea260fffc4a49145ecf67c610b15
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332337"
---
# <a name="compiler-error-c2884"></a>编译器错误 C2884

"name"：由 using 声明引入，与本地函数 "function" 冲突

尝试多次定义函数。 第一个定义是本地定义。 第二种情况是来自带有声明的命名空间 **`using`** 。

下面的示例生成 C2884：

```cpp
// C2884.cpp
namespace A {
   void z(int);
}

void f() {
   void z(int);
   using A::z;   // C2884 z is already defined
}
```
