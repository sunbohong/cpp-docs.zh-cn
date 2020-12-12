---
description: 了解更多：编译器错误 C3519
title: 编译器错误 C3519
ms.date: 11/04/2016
f1_keywords:
- C3519
helpviewer_keywords:
- C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
ms.openlocfilehash: f8eb90620894627beab450275c6725d665d837e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113074"
---
# <a name="compiler-error-c3519"></a>编译器错误 C3519

"invalid_param"： embedded_idl 特性的参数无效

参数被传递到 #import 的 `embedded_idl` 属性， [](../../preprocessor/hash-import-directive-cpp.md)但编译器不能识别参数。

允许的唯一参数 `embedded_idl` 是 `emitidl` 和 `no_emitidl` 。

下面的示例生成 C3519：

```cpp
// C3519.cpp
// compile with: /LD
[module(name="MyLib2")];
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")
// C3519
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")
// OK
```
