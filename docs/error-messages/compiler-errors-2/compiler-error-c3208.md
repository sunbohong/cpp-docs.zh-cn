---
description: 了解更多：编译器错误 C3208
title: 编译器错误 C3208
ms.date: 11/04/2016
f1_keywords:
- C3208
helpviewer_keywords:
- C3208
ms.assetid: 6d060bfe-52cf-4599-8f70-bdeb5a670df3
ms.openlocfilehash: bd76a209fa3736449e8816473d0dee12daa93a61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173943"
---
# <a name="compiler-error-c3208"></a>编译器错误 C3208

“function”: 类模板“class”的模板参数列表与模板 template 参数“parameter”的模板参数列表不匹配

模板 template 参数的模板参数数量与提供的类模板不同。

下面的示例生成 C3208：

```cpp
// C3208.cpp
template <template <class T> class TT >
int f();

template <class T1, class T2>
struct S;

template <class T1>
struct R;

int i = f<S>();   // C3208
// try the following line instead
// int i = f<R>();
```
