---
description: 详细了解：编译器警告 (级别 4) C4429
title: 编译器警告（等级 4）C4429
ms.date: 11/04/2016
f1_keywords:
- C4429
helpviewer_keywords:
- C4429
ms.assetid: a3e4cf1f-a869-4e47-834a-850c21eb5297
ms.openlocfilehash: dbd552eb2f8e021f8bf7b7747e2a8aee49bb05a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241360"
---
# <a name="compiler-warning-level-4-c4429"></a>编译器警告（等级 4）C4429

通用字符名称可能不完整或格式不正确

编译器检测到可能是格式不正确的通用字符名称的字符序列。 通用字符名称 `\u` 后跟四个十六进制数字，或 `\U` 后跟8个十六进制数字。

下面的示例生成 C4429：

```cpp
// C4429.cpp
// compile with: /W4 /WX
int \ug0e4 = 0;   // C4429
// Try the following line instead:
// int \u00e4 = 0;   // OK, a well-formed universal character name.
```
