---
description: 了解更多：编译器错误 C2756
title: 编译器错误 C2756
ms.date: 11/04/2016
f1_keywords:
- C2756
helpviewer_keywords:
- C2756
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
ms.openlocfilehash: 94a3211bd45136f74e87a971aa3fd3717355f8d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336198"
---
# <a name="compiler-error-c2756"></a>编译器错误 C2756

“模板类型”: 部分专用化中不允许有默认模板自变量

部分专用化的模板不能包含默认自变量。

下面的示例生成 C2756，并演示如何修复此错误：

```cpp
// C2756.cpp
template <class T>
struct S {};

template <class T=int>
// try the following line instead
// template <class T>
struct S<T*> {};   // C2756
```
