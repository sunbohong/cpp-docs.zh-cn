---
description: 了解更多：编译器错误 C2808
title: 编译器错误 C2808
ms.date: 11/04/2016
f1_keywords:
- C2808
helpviewer_keywords:
- C2808
ms.assetid: 3d745102-d3b3-4735-a7d2-ad42d5bf3cfa
ms.openlocfilehash: bdc47ff480afa77c22784536c1ed6337358e3d87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320569"
---
# <a name="compiler-error-c2808"></a>编译器错误 C2808

一元运算符 "operator operator" 的形参太多

一元运算符具有一个非 void 参数列表。

下面的示例生成 C2808：

```cpp
// C2808.cpp
// compile with: /c
class X {
public:
   X operator! ( X );   // C2808 nonvoid parameter list
   X operator! ( void );   // OK
};
```
