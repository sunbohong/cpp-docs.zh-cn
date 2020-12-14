---
description: 了解更多：编译器错误 C2802
title: 编译器错误 C2802
ms.date: 11/04/2016
f1_keywords:
- C2802
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
ms.openlocfilehash: ff526306b89a5679147a30e7b3cd2f07ddc2b8f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297442"
---
# <a name="compiler-error-c2802"></a>编译器错误 C2802

静态成员 "operator operator" 没有形参

成员函数声明的运算符 **`static`** 必须具有至少一个参数。

下面的示例生成 C2802：

```cpp
// C2802.cpp
// compile with: /clr /c
ref class A {
   static operator+ ();   // C2802
   static operator+ (A^, A^);   // OK
};
```
