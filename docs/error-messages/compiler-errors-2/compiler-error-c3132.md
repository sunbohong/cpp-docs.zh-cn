---
description: 了解更多：编译器错误 C3132
title: 编译器错误 C3132
ms.date: 11/04/2016
f1_keywords:
- C3132
helpviewer_keywords:
- C3132
ms.assetid: d54a3d12-336a-4ed0-ad4e-43cddac33b5e
ms.openlocfilehash: e81ddcb977342a687dce329239a590f90eca67ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177388"
---
# <a name="compiler-error-c3132"></a>编译器错误 C3132

"函数参数"：参数数组只能应用于 "一维托管数组" 类型的形参

<xref:System.ParamArrayAttribute>特性被应用于不是单维度数组的参数。

下面的示例生成 C3132：

```cpp
// C3132.cpp
// compile with: /clr /c
using namespace System;
void f( [ParamArray] Int32[,] );   // C3132
void g( [ParamArray] Int32[] );   // C3132

void h( [ParamArray] array<Char ^> ^ MyArray );   // OK
```
