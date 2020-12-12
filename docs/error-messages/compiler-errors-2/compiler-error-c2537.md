---
description: 了解更多：编译器错误 C2537
title: 编译器错误 C2537
ms.date: 11/04/2016
f1_keywords:
- C2537
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
ms.openlocfilehash: 46603ded270b4702d4b7d4de97352547c5f503f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302031"
---
# <a name="compiler-error-c2537"></a>编译器错误 C2537

"说明符"：非法的链接规范

可能的原因：

1. 不支持链接说明符。 仅支持 "C" 链接说明符。

1. 为一组重载函数中的多个函数指定了 "C" 链接。 这是不允许的。

下面的示例生成 C2537：

```cpp
// C2537.cpp
// compile with: /c
extern "c" void func();   // C2537
extern "C" void func2();   // OK
```
