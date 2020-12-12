---
description: 了解更多：编译器错误 C2897
title: 编译器错误 C2897
ms.date: 11/04/2016
f1_keywords:
- C2897
helpviewer_keywords:
- C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
ms.openlocfilehash: b1a1f66987aa4bbd01fdf12f88f8933e3436938a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270870"
---
# <a name="compiler-error-c2897"></a>编译器错误 C2897

析构函数/终结器不能是函数模板

析构函数或终结器不能重载，因此将析构函数声明为模板 (将不允许定义一组析构函数) 。

## <a name="examples"></a>示例

下面的示例生成 C2897。

```cpp
// C2897.cpp
// compile with: /c
class X {
public:
   template<typename T> ~X() {}   // C2897
};
```

下面的示例生成 C2897。

```cpp
// C2897_b.cpp
// compile with: /c /clr
ref struct R2 {
protected:
   template<typename T> !R2(){}   // C2897 error
};
```
