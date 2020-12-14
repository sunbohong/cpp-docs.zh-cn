---
description: 了解更多：编译器错误 C3283
title: 编译器错误 C3283
ms.date: 11/04/2016
f1_keywords:
- C3283
helpviewer_keywords:
- C3283
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
ms.openlocfilehash: 577f3fa6c3316c58bf6e9dca94b22a168a451b17
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311872"
---
# <a name="compiler-error-c3283"></a>编译器错误 C3283

“类型”: 接口不能包含实例构造函数

CLR [接口](../../extensions/interface-class-cpp-component-extensions.md) 不能包含实例构造函数。  允许使用静态构造函数。

以下示例生成 C3283:

```cpp
// C3283.cpp
// compile with: /clr
interface class I {
   I();   // C3283
};
```

可能的解决方法：

```cpp
// C3283b.cpp
// compile with: /clr /c
interface class I {
   static I(){}
};
```
