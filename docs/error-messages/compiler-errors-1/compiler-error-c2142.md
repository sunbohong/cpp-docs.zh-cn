---
description: 了解更多：编译器错误 C2142
title: 编译器错误 C2142
ms.date: 11/04/2016
f1_keywords:
- C2142
helpviewer_keywords:
- C2142
ms.assetid: d0dbe10e-0952-49a4-8b33-e82fb7558b19
ms.openlocfilehash: 65bd189fe99bb54549e458b093b72d8e47b840a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235523"
---
# <a name="compiler-error-c2142"></a>编译器错误 C2142

函数声明不同，仅在其中一个中指定了变量参数

函数的一个声明包含变量参数列表。 其他声明不存在。 仅限 ANSI C ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 。

下面的示例生成 C2142：

```c
// C2142.c
// compile with: /Za /c
void func();
void func( int, ... );   // C2142
void func2( int, ... );   // OK
```
