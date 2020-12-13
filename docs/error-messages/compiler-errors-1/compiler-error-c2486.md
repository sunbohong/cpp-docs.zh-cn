---
description: 了解更多：编译器错误 C2486
title: 编译器错误 C2486
ms.date: 11/04/2016
f1_keywords:
- C2486
helpviewer_keywords:
- C2486
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
ms.openlocfilehash: c45e0bdb0f515743694fe372bea3afdb24e00177
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339353"
---
# <a name="compiler-error-c2486"></a>编译器错误 C2486

仅在具有 "naked" 特性的函数中允许 "__LOCAL_SIZE"

在内联程序集函数中，该名称 `__LOCAL_SIZE` 将保留给用 [naked](../../cpp/naked-cpp.md) 特性声明的函数。

下面的示例生成 C2486：

```cpp
// C2486.cpp
// processor: x86
void __declspec(naked) f1() {
   __asm {
      mov   eax,   __LOCAL_SIZE
   }
}
void f2() {
   __asm {
      mov   eax,   __LOCAL_SIZE   // C2486
   }
}
```
