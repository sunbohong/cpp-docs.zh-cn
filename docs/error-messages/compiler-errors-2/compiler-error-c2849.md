---
description: 了解更多：编译器错误 C2849
title: 编译器错误 C2849
ms.date: 11/04/2016
f1_keywords:
- C2849
helpviewer_keywords:
- C2849
ms.assetid: e28f6b3e-e0e7-4f92-b006-ebaa81d368e6
ms.openlocfilehash: 890d8e9d257e1efc20058f0e2f47ccf04ea3217b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260184"
---
# <a name="compiler-error-c2849"></a>编译器错误 C2849

"析构函数"：接口不能有析构函数

Visual C++ [接口](../../cpp/interface.md) 不能包含析构函数。

下面的示例生成 C2849：

```cpp
// C2849.cpp
// compile with: /c
__interface C {
   ~C();   // C2849 destructor not allowed in an interface
};
```
