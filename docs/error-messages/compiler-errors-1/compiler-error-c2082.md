---
description: 了解更多：编译器错误 C2082
title: 编译器错误 C2082
ms.date: 11/04/2016
f1_keywords:
- C2082
helpviewer_keywords:
- C2082
ms.assetid: 87a6d442-157c-46e8-9bff-8388f8338ae0
ms.openlocfilehash: 957699338d253ee2438060b27a0089a654fc4f9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316617"
---
# <a name="compiler-error-c2082"></a>编译器错误 C2082

形参“identifier”的重定义

已在函数体中重新声明了函数的形参。 若要解决此错误，请删除重新定义。

以下示例生成 C2082：

```cpp
// C2082.cpp
void func(int i) {
   int i;   // C2082
   int ii;   // OK
}
```
