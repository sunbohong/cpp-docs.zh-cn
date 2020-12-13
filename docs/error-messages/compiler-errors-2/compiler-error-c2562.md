---
description: 了解更多：编译器错误 C2562
title: 编译器错误 C2562
ms.date: 11/04/2016
f1_keywords:
- C2562
helpviewer_keywords:
- C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
ms.openlocfilehash: 9e9da8a7463b450073f4b537ec36512242995760
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338703"
---
# <a name="compiler-error-c2562"></a>编译器错误 C2562

"identifier"： "void" 函数返回值

函数被声明为， **`void`** 但会返回一个值。

此错误可能是由不正确的函数原型导致的。

如果在函数声明中指定返回类型，则可能会修复此错误。

下面的示例生成 C2562：

```cpp
// C2562.cpp
// compile with: /c
void testfunc() {
   int i;
   return i;   // C2562 delete the return to resolve
}
```
