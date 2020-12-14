---
description: 了解更多：编译器错误 C2943
title: 编译器错误 C2943
ms.date: 11/04/2016
f1_keywords:
- C2943
helpviewer_keywords:
- C2943
ms.assetid: ede6565e-d892-44c0-8eee-c69545f3be2e
ms.openlocfilehash: f85000ae554e25f2ca783b605b036abb3f04eadb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249576"
---
# <a name="compiler-error-c2943"></a>编译器错误 C2943

“class”：type-class-id 重新定义为模板的类形参数

你不能使用泛型类或模板类，而是改用符号作为泛型或模板类型参数。

以下示例生成 C2943：

```cpp
// C2943.cpp
// compile with: /c
template<class T>
class List {};

template<class List<int> > class MyList;   // C2943
template<class T >  class MyList;
```
