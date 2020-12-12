---
description: 了解更多：编译器错误 C2062
title: 编译器错误 C2062
ms.date: 11/04/2016
f1_keywords:
- C2062
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
ms.openlocfilehash: ef477fba9bb1208076dd6969cb78b7495d5536e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328646"
---
# <a name="compiler-error-c2062"></a>编译器错误 C2062

意外的类型 "type"

编译器不需要类型名称。

下面的示例生成 C2062：

```cpp
// C2062.cpp
// compile with: /c
struct A {  : int l; };   // C2062
struct B { private: int l; };   // OK
```

由于编译器处理构造函数的参数列表中未定义的类型的方式，也可能会发生 C2062。 如果编译器遇到未定义的 (拼写错误？ ) 类型，它假定构造函数是一个表达式，并 C2062 问题。 若要解决此问题，请仅使用构造函数参数列表中的已定义类型。
