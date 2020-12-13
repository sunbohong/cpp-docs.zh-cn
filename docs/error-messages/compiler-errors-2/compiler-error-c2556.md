---
description: 了解更多：编译器错误 C2556
title: 编译器错误 C2556
ms.date: 11/04/2016
f1_keywords:
- C2556
helpviewer_keywords:
- C2556
ms.assetid: fc4399ad-45b3-49fd-be1f-0b13956a595a
ms.openlocfilehash: 6c2233e10e763e959511c6b435e0d894e921905a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134480"
---
# <a name="compiler-error-c2556"></a>编译器错误 C2556

"identifier"：重载函数只在返回类型上不同

重载函数具有不同的返回类型，但具有相同的参数列表。 每个重载函数都必须具有一个不同的形参列表。

下面的示例生成 C2556：

```cpp
// C2556.cpp
// compile with: /c
class C {
   int func();
   double func();   // C2556
   int func(int i);   // ok parameter lists differ
};
```
