---
description: 了解更多：编译器错误 C2800
title: 编译器错误 C2800
ms.date: 11/04/2016
f1_keywords:
- C2800
helpviewer_keywords:
- C2800
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
ms.openlocfilehash: 7adcb8e24bd7b3f3941260a9cceaa5157334ae8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297500"
---
# <a name="compiler-error-c2800"></a>编译器错误 C2800

无法重载 "operator operator"

无法重载以下运算符：) 成员访问 (`.` ，指向成员的指针 (`.*`) ，范围解析 () `::` ，条件表达式 (`? :`) ，和 **`sizeof`** 。

下面的示例生成 C2800：

```cpp
// C2800.cpp
// compile with: /c
class C {
   operator:: ();   // C2800
};
```
