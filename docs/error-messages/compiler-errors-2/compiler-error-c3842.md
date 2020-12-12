---
description: 了解更多：编译器错误 C3842
title: 编译器错误 C3842
ms.date: 11/04/2016
f1_keywords:
- C3842
helpviewer_keywords:
- C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
ms.openlocfilehash: dd5cff7b4a381ca976138720d8af192d594c7836
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255413"
---
# <a name="compiler-error-c3842"></a>编译器错误 C3842

“函数”: 不支持在 WinRT 或托管类型的成员函数上使用“const”和“volatile”限定符

在 Windows 运行时或托管类型的成员函数上不支持[const](../../cpp/const-cpp.md)和[volatile](../../cpp/volatile-cpp.md) 。

下面的示例生成 C3842：

```cpp
// C3842a.cpp
// compile with: /clr /c
public ref struct A {
   void f() const {}   // C3842
   void f() volatile {}   // C3842

   void f() {}
};
```
