---
description: 了解更多：编译器错误 C2755
title: 编译器错误 C2755
ms.date: 11/04/2016
f1_keywords:
- C2755
helpviewer_keywords:
- C2755
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
ms.openlocfilehash: dcf597505afb170aaf87644a7482a56dc2fdc73c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336218"
---
# <a name="compiler-error-c2755"></a>编译器错误 C2755

"param"：部分专用化的非类型参数必须是简单标识符

非类型参数必须是简单标识符，编译器可以在编译时解析为单个标识符或常量值。

下面的示例生成 C2755：

```cpp
// C2755.cpp
template<int I, int J>
struct A {};

template<int I>
struct A<I,I*5> {};   // C2755
// try the following line instead
// struct A<I,5> {};
```
