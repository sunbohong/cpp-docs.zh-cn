---
description: 了解更多：编译器错误 C2514
title: 编译器错误 C2514
ms.date: 11/04/2016
f1_keywords:
- C2514
helpviewer_keywords:
- C2514
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
ms.openlocfilehash: 3999a5a65df08142b68e7257b257d39d1b5245e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212813"
---
# <a name="compiler-error-c2514"></a>编译器错误 C2514

"class"：类没有构造函数

类、结构或联合没有带有与用于实例化参数的参数列表相匹配的参数列表的构造函数。

必须完全声明类，然后才能对其进行实例化。

下面的示例生成 C2514：

```cpp
// C2514.cpp
// compile with: /c
class f;

class g {
public:
    g (int x);
};

class fmaker {
   f *func1() {
      return new f(2);   // C2514
   }

   g *func2() {
      return new g(2);   // OK
   }
};
```
