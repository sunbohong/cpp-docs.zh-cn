---
description: 了解更多：编译器错误 C2466
title: 编译器错误 C2466
ms.date: 11/04/2016
f1_keywords:
- C2466
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
ms.openlocfilehash: 68ff57de2c0287f24ac84466ac8053bf73f88a95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333831"
---
# <a name="compiler-error-c2466"></a>编译器错误 C2466

不能分配常量大小为0的数组

使用大小0来分配或声明数组。 数组大小的常量表达式必须是大于零的整数。 带有零下标的数组声明仅对类、结构或联合成员合法，并且仅适用于 Microsoft extension ([/ze](../../build/reference/za-ze-disable-language-extensions.md)) 。

下面的示例生成 C2466：

```cpp
// C2466.cpp
// compile with: /c
int i[0];   // C2466
int j[1];   // OK
char *p;
```
