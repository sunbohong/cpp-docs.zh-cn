---
description: 了解更多：编译器错误 C3354
title: 编译器错误 C3354
ms.date: 11/04/2016
f1_keywords:
- C3354
helpviewer_keywords:
- C3354
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
ms.openlocfilehash: cb2c110471b95010e56677608725e5d6abeaa5e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245312"
---
# <a name="compiler-error-c3354"></a>编译器错误 C3354

“%$I”：该函数用于创建不能有返回类型“type”的委托

以下类型作为的返回类型无效 **`delegate`** ：

- 指向函数的指针

- 指向成员的指针

- 指向成员函数的指针

- 对函数的引用

- 对成员函数的引用

以下示例生成 C3354：

```cpp
// C3354_2.cpp
// compile with: /clr /c
using namespace System;
typedef void ( *VoidPfn )();

delegate VoidPfn func(); // C3354
// try the following line instead
// delegate  void func();
```
