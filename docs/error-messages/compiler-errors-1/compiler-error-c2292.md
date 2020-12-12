---
description: 了解更多：编译器错误 C2292
title: 编译器错误 C2292
ms.date: 11/04/2016
f1_keywords:
- C2292
helpviewer_keywords:
- C2292
ms.assetid: 256b392f-2b8f-4162-b578-e7633984e162
ms.openlocfilehash: fb3630edc1aa3fc3aeb1b90d3ab79b17c775fa61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268244"
---
# <a name="compiler-error-c2292"></a>编译器错误 C2292

"identifier"：最佳 case 继承表示形式： "representation1" 已声明，但需要 "representation2"

用 [/vmb](../../build/reference/vmb-vmg-representation-method.md) ( "最佳情况下，" 始终 "表示形式编译以下代码) 导致 C2292。

```cpp
// C2292.cpp
// compile with: /vmb
class __single_inheritance X;

struct A { };
struct B { };
struct X : A, B { };  // C2292, X uses multiple inheritance
```
