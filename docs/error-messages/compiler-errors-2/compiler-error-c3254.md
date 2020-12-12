---
description: 了解更多：编译器错误 C3254
title: 编译器错误 C3254
ms.date: 11/04/2016
f1_keywords:
- C3254
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
ms.openlocfilehash: 7d0084f52060803cd99b973c9f6105fc8915c2aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194210"
---
# <a name="compiler-error-c3254"></a>编译器错误 C3254

"explicit override"：类包含显式重写 "override"，但不从包含函数声明的接口派生

[显式重写](../../cpp/explicit-overrides-cpp.md)方法时，包含重写的类必须直接或间接从包含要重写的函数的类型派生。

下面的示例生成 C3254：

```cpp
// C3254.cpp
__interface I
{
   void f();
};

__interface I1 : I
{
};

struct A /* : I1 */
{
   void I1::f()
   {   // C3254, uncomment : I1 to resolve this C3254
   }
};

int main()
{
}
```
