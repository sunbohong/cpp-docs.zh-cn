---
description: 了解更多：编译器错误 C2090
title: 编译器错误 C2090
ms.date: 11/04/2016
f1_keywords:
- C2090
helpviewer_keywords:
- C2090
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
ms.openlocfilehash: 224f900a20d57a35a6a6c6dcc2dc95b09c596403
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251903"
---
# <a name="compiler-error-c2090"></a>编译器错误 C2090

函数返回数组

函数不能返回数组。 改为返回指向数组的指针。

下面的示例生成 C2090：

```cpp
// C2090.cpp
int func1(void)[] {}   // C2090
```

可能的解决方法：

```cpp
// C2090b.cpp
// compile with: /c
int* func2(int * i) {
   return i;
}
```
