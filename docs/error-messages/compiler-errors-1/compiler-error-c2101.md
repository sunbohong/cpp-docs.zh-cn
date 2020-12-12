---
description: 了解更多：编译器错误 C2101
title: 编译器错误 C2101
ms.date: 11/04/2016
f1_keywords:
- C2101
helpviewer_keywords:
- C2101
ms.assetid: 42f0136f-8cc1-4f2b-be1c-721ec9278e66
ms.openlocfilehash: b41aa520d0aba3970689bf0bb5d65db5effb36aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278566"
---
# <a name="compiler-error-c2101"></a>编译器错误 C2101

常量上的“&”

address-of 运算符 ( `&` ) 必须将左值作为操作数。

下面的示例生成 C2101：

```cpp
// C2101.cpp
int main() {
   char test;
   test = &'a';   // C2101
   test = 'a';   // OK
}
```
