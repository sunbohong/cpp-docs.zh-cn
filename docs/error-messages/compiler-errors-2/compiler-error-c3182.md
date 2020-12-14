---
description: 了解更多：编译器错误 C3182
title: 编译器错误 C3182
ms.date: 11/04/2016
f1_keywords:
- C3182
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
ms.openlocfilehash: d4cf5d86a553a597636c09f72ff3a068e2a6b9b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242022"
---
# <a name="compiler-error-c3182"></a>编译器错误 C3182

"class"：托管或 WinRTtype 中的成员 using 声明或访问声明非法

[使用](../../cpp/using-declaration.md)声明在托管类的所有形式内无效。

下例生成了 C3182，并演示了如何对其进行修复。

```cpp
// C3182a.cpp
// compile with: /clr /c
ref struct B {
   void mf(int) {
   }
};

ref struct D : B {
   using B::mf;   // C3182, delete to resolve
   void mf(char) {
   }
};
```
