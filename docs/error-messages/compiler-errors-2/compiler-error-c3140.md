---
description: 了解更多：编译器错误 C3140
title: 编译器错误 C3140
ms.date: 11/04/2016
f1_keywords:
- C3140
helpviewer_keywords:
- C3140
ms.assetid: 122f8943-fac3-4db8-a3a8-2c5d19233de6
ms.openlocfilehash: d4655589c5901a0ba609bde0cb5cb96907e087c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304215"
---
# <a name="compiler-error-c3140"></a>编译器错误 C3140

同一编译单元中不能有多个 "module" 特性

每个项目只能定义一次 [module](../../windows/attributes/module-cpp.md) 特性。

下面的示例生成 C3140：

```cpp
// C3140.cpp
// compile with: /c
[emitidl];
[module(name = "MyLibrary")];
[module(name = "MyLibrary2")];   // C3140
```
