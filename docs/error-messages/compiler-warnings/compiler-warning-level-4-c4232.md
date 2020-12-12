---
description: 详细了解：编译器警告 (级别 4) C4232
title: 编译器警告（等级 4）C4232
ms.date: 11/04/2016
f1_keywords:
- C4232
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
ms.openlocfilehash: 272fdcbc856ef5e86a8ff043b5aeab98a36413a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291410"
---
# <a name="compiler-warning-level-4-c4232"></a>编译器警告（等级 4）C4232

使用了非标准扩展： "identifier"： dllimport "dllimport" 的地址不是静态的，不保证标识

在 "Microsoft extension (/Ze) 下，你可以提供一个非静态值作为使用修饰符声明的函数的地址 **`dllimport`** 。 在 ANSI 兼容性 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 下，这会导致错误。

下面的示例生成 C4232：

```c
// C4232.c
// compile with: /W4 /Ze /c
int __declspec(dllimport) f();
int (*pfunc)() = &f;   // C4232
```
