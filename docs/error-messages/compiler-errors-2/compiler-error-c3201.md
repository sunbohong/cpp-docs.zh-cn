---
description: 了解更多：编译器错误 C3201
title: 编译器错误 C3201
ms.date: 11/04/2016
f1_keywords:
- C3201
helpviewer_keywords:
- C3201
ms.assetid: ec19cd64-1789-40a3-b2db-dff2852b9d98
ms.openlocfilehash: 3cd6e037cd9dbb0638040e2f3eca61dab1dabb46
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330646"
---
# <a name="compiler-error-c3201"></a>编译器错误 C3201

类模板“template”的模板参数列表与模板参数“template”的模板参数列表不匹配

将自变量中的类模板传递给了不使用模板参数的类模板，或为默认模板自变量传递了数量不匹配的模板自变量。

```cpp
// C3201.cpp
template<typename T1, typename T2>
class X1
{
};

template<template<typename T> class U = X1>   // C3201
class X2
{
};

template<template<typename T, typename V> class U = X1>   // OK
class X3
{
};
```
