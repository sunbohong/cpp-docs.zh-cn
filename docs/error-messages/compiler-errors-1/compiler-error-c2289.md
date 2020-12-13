---
description: 了解更多：编译器错误 C2289
title: 编译器错误 C2289
ms.date: 11/04/2016
f1_keywords:
- C2289
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
ms.openlocfilehash: ba9af908af6defaccd6825ce3dad412ad6914c77
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185955"
---
# <a name="compiler-error-c2289"></a>编译器错误 C2289

多次使用同一类型限定符

类型声明或定义 (**`const`** 、 **`volatile`** 、 **`signed`** 或) 多次使用类型限定符 **`unsigned`** ，从而导致 ANSI 兼容性 (**/za**) 出现错误。

下面的示例生成 C2286：

```cpp
// C2289.cpp
// compile with: /Za /c
volatile volatile int i;   // C2289
volatile int j;   // OK
```
