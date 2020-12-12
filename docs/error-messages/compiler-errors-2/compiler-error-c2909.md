---
description: 了解更多：编译器错误 C2909
title: 编译器错误 C2909
ms.date: 11/04/2016
f1_keywords:
- C2909
helpviewer_keywords:
- C2909
ms.assetid: 1c9df8ae-925d-4002-a5f8-a71413c45f9e
ms.openlocfilehash: c2a3ba74f87edb0f1958910d04820316508f6567
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270636"
---
# <a name="compiler-error-c2909"></a>编译器错误 C2909

“identifier”: 函数模板的显式实例化需要返回类型

函数模板的显式实例化需要显式指定返回类型。 隐式返回类型指定不起作用。

下面的示例生成 C2909：

```cpp
// C2909.cpp
// compile with: /c
template<class T> int f(T);
template f<int>(int);         // C2909
template int f<int>(int);   // OK
```
