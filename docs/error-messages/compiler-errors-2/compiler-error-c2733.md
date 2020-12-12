---
description: 了解更多：编译器错误 C2733
title: 编译器错误 C2733
ms.date: 11/04/2016
f1_keywords:
- C2733
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
ms.openlocfilehash: f957be13b8c1de1ee3ada98ffd42f0d89fc7755c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123196"
---
# <a name="compiler-error-c2733"></a>编译器错误 C2733

不允许使用重载函数 "function" 的第二个 C 链接

用 C 链接声明了多个重载函数。 使用 C 链接时，只有一个指定函数的形式可以是外部的。 由于重载函数具有相同的未修饰名称，因此它们不能与 C 程序一起使用。

下面的示例生成 C2733：

```cpp
// C2733.cpp
extern "C" {
   void F1(int);
}

extern "C" {
   void F1();   // C2733
   // try the following line instead
   // void F2();
}
```
