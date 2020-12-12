---
description: 了解更多：编译器错误 C3179
title: 编译器错误 C3179
ms.date: 11/04/2016
f1_keywords:
- C3179
helpviewer_keywords:
- C3179
ms.assetid: 60d7e41b-25fd-48ac-8b79-830c062f4dcd
ms.openlocfilehash: 5f4b573c822eff68d972517f9fac093071cf2a0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174151"
---
# <a name="compiler-error-c3179"></a>编译器错误 C3179

不允许未命名的托管类型或 WinRT 类型

所有 CLR 与 WinRT 类和结构都必须具有名称。

下面的示例生成 C3179，并演示如何修复此错误：

```cpp
// C3179a.cpp
// compile with: /clr /c
typedef value struct { // C3179
// try the following line instead
// typedef value struct MyStruct {
   int i;
} V;
```
