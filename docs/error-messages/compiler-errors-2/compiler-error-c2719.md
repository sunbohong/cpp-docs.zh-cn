---
description: 了解更多：编译器错误 C2719
title: 编译器错误 C2719
ms.date: 11/04/2016
f1_keywords:
- C2719
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
ms.openlocfilehash: 61e01107d5681c4bab39b06b00293ecdbeb9fc9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320717"
---
# <a name="compiler-error-c2719"></a>编译器错误 C2719

“parameter”：不对齐具有 __declspec(align('#')) 的形参

[](../../cpp/align-cpp.md) **`__declspec`** 函数参数上不允许使用 align 修饰符。 函数参数的对齐方式由所使用的调用约定控制。 有关详细信息，请参阅 [调用约定](../../cpp/calling-conventions.md)。

以下示例将生成 C2719，并演示如何修复此错误：

```cpp
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```
