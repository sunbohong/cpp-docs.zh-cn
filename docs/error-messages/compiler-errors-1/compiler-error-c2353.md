---
description: 了解更多：编译器错误 C2353
title: 编译器错误 C2353
ms.date: 11/04/2016
f1_keywords:
- C2353
helpviewer_keywords:
- C2353
ms.assetid: d57f8f77-d9b1-4bba-a940-87ec269ad183
ms.openlocfilehash: d2fc96a74256f37b6c7cb9bc9515d46ad70fd83d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291878"
---
# <a name="compiler-error-c2353"></a>编译器错误 C2353

不允许使用异常规范

不允许对托管类的成员函数使用异常规范。

下面的示例生成 C2353：

```cpp
// C2353.cpp
// compile with: /clr /c
ref class X {
   void f() throw(int);   // C2353
   void f();   // OK
};
```
