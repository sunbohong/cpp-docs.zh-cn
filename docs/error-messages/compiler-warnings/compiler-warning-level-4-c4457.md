---
description: 详细了解：编译器警告 (级别 4) C4457
title: 编译器警告 (等级 4) C4457
ms.date: 11/04/2016
f1_keywords:
- C4457
helpviewer_keywords:
- C4457
ms.assetid: 02fd149a-917d-4f67-97a6-eb714572271f
ms.openlocfilehash: 8898189668eba95619e6bd0d0ccf1cb8ca3afdfe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251409"
---
# <a name="compiler-warning-level-4-c4457"></a>编译器警告 (等级 4) C4457

> "*identifier*" 的声明隐藏了函数参数

局部范围内的 *标识符* 声明隐藏了具有相同名称的函数参数的声明。 此警告使你知道本地范围内的 *标识符* 引用解析为本地声明的版本，而不是参数，这不一定是你的意图。 若要解决此问题，我们建议你提供不与参数名称冲突的局部变量名称。

## <a name="example"></a>示例

下面的示例生成 C4457，因为中的参数 `x` 和本地 `x` 变量 `member_fn` 具有相同的名称。 若要解决此问题，请使用不同的名称作为参数和局部变量。

```cpp
// C4457_hide.cpp
// compile with: cl /W4 /c C4457_hide.cpp

struct S {
    void member_fn(unsigned x) {
        double a = 0;
        for (int x = 0; x < 10; ++x) {  // C4457
            a += x; // uses local x
        }
        a += x; // uses parameter x
    }
} s;
```
