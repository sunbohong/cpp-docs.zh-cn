---
description: 了解更多：编译器错误 C2765
title: 编译器错误 C2765
ms.date: 11/04/2016
f1_keywords:
- C2765
helpviewer_keywords:
- C2765
ms.assetid: 47ad86f3-a7e0-47ad-85ff-0f5534458cb9
ms.openlocfilehash: 496f28645dddc0ac426716cc80ee0d6760042ad7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239540"
---
# <a name="compiler-error-c2765"></a>编译器错误 C2765

"function"：函数模板的显式专用化不能有任何默认参数

函数模板的显式专用化中不允许使用默认参数。 有关详细信息，请参阅 [函数模板的显式专用化](../../cpp/explicit-specialization-of-function-templates.md)。

下面的示例生成 C2765：

```cpp
// C2765.cpp
template<class T> void f(T t) {};

template<> void f<char>(char c = 'a') {}   // C2765
// try the following line instead
// template<> void f<char>(char c) {}
```
