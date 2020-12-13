---
description: 了解更多：编译器错误 C2460
title: 编译器错误 C2460
ms.date: 11/04/2016
f1_keywords:
- C2460
helpviewer_keywords:
- C2460
ms.assetid: d969fca9-3ac5-4e4e-88fc-df05510e2093
ms.openlocfilehash: 6a6b521b356d4005906e97b085271369f2624c46
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341849"
---
# <a name="compiler-error-c2460"></a>编译器错误 C2460

"identifier1"：使用正在定义的 "identifier2"

类或结构 (`identifier2`) 在)  (声明为自身的成员 `identifier1` 。 不允许递归定义类和结构。

下面的示例生成 C2460：

```cpp
// C2460.cpp
class C {
   C aC;    // C2460
};
```

请改用类中的指针引用。

```cpp
// C2460.cpp
class C {
   C * aC;    // OK
};
```
