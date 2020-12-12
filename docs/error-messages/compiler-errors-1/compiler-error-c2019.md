---
description: 了解更多：编译器错误 C2019
title: 编译器错误 C2019
ms.date: 11/04/2016
f1_keywords:
- C2019
helpviewer_keywords:
- C2019
ms.assetid: 4f37b1e1-9eca-418f-a4c3-141e8512d7b6
ms.openlocfilehash: 5b30bdb8eace513572152d0f33da5f591e21bd6e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283922"
---
# <a name="compiler-error-c2019"></a>编译器错误 C2019

应为预处理器指令，却找到“character”

字符后跟 `#` 符号，但它不是预处理器指令的第一个字母。

下面的示例生成 C2019：

```cpp
// C2019.cpp
#!define TRUE 1   // C2019
```

可能的解决方法：

```cpp
// C2019b.cpp
// compile with: /c
#define TRUE 1
```
