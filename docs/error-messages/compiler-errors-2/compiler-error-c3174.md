---
description: 了解更多：编译器错误 C3174
title: 编译器错误 C3174
ms.date: 11/04/2016
f1_keywords:
- C3174
helpviewer_keywords:
- C3174
ms.assetid: fe6b3b5a-8196-485f-a45f-0b2e51df4086
ms.openlocfilehash: 28a2daae597e93d8aa3745ad16eed491e3ea2e87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242088"
---
# <a name="compiler-error-c3174"></a>编译器错误 C3174

未指定模块特性

使用 Visual C++ 特性的程序也不会使用 [module](../../windows/attributes/module-cpp.md) 属性，该属性在使用特性的任何程序中是必需的。

下面的示例生成 C3174：

```cpp
// C3174.cpp
// C3174 expected
// uncomment the following line to resolve this C3174
// [module(name="x")];
[export]
struct S
{
   int i;
};

int main()
{
}
```
