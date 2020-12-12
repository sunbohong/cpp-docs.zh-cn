---
description: 了解更多：编译器错误 C2710
title: 编译器错误 C2710
ms.date: 11/04/2016
f1_keywords:
- C2710
helpviewer_keywords:
- C2710
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
ms.openlocfilehash: ea9e4eaefa023362647f418be16a72ee14fbd044
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320852"
---
# <a name="compiler-error-c2710"></a>编译器错误 C2710

"构造"： "__declspec (修饰符) " 只能应用于返回指针的函数

其返回值为指针的函数是可以应用的唯一构造 `modifier` 。

下面的示例生成 C2710：

```cpp
// C2710.cpp
__declspec(restrict) void f();   // C2710
// try the following line instead
__declspec(restrict) int * g();
```
