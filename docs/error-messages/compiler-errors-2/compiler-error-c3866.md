---
description: 了解更多：编译器错误 C3866
title: 编译器错误 C3866
ms.date: 11/04/2016
f1_keywords:
- C3866
helpviewer_keywords:
- C3866
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
ms.openlocfilehash: fceb8ed41a3cbfc287f4c1115cd0502ce8506925
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222861"
---
# <a name="compiler-error-c3866"></a>编译器错误 C3866

缺少参数列表的函数调用

在非静态成员函数中，析构函数或终结器调用没有参数列表。

下面的示例生成 C3866：

```cpp
// C3866.cpp
// compile with: /c
class C {
   ~C();
   void f() {
      this->~C;   // C3866
      this->~C();   // OK
   }
};
```
