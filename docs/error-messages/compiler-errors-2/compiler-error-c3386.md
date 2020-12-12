---
description: 了解更多：编译器错误 C3386
title: 编译器错误 C3386
ms.date: 11/04/2016
f1_keywords:
- C3386
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
ms.openlocfilehash: 5bc80abe7c43e30c4114d0f3ffd7733c8ea3e9d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115893"
---
# <a name="compiler-error-c3386"></a>编译器错误 C3386

> "*type-name*"： `__declspec(dllexport)` / `__declspec(dllimport)` 不能应用于托管或 WinRT 类型

[`dllimport`](../../cpp/dllexport-dllimport.md)和 [`dllexport`](../../cpp/dllexport-dllimport.md) **`__declspec`** 修饰符在托管或 Windows 运行时类型上无效。

下面的示例生成 C3386，并演示如何修复此错误：

```cpp
// C3386.cpp
// compile with: /clr /c
ref class __declspec(dllimport) X1 {   // C3386
// try the following line instead
// ref class X1 {
};
```
