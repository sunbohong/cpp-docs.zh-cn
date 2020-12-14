---
description: 详细了解：编译器警告 (级别 4) C4456
title: 编译器警告 (等级 4) C4456
ms.date: 11/04/2016
f1_keywords:
- C4456
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
ms.openlocfilehash: f066de07b0c6bf7a7b5de3143909e402b0fedde3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241308"
---
# <a name="compiler-warning-level-4-c4456"></a>编译器警告 (等级 4) C4456

> "*identifier*" 的声明隐藏了上一个本地声明

局部范围内的 *标识符* 声明隐藏了同一名称的上一个本地声明的声明。 此警告使你知道本地范围内的 *标识符* 引用解析为本地声明的版本，而不是之前的本地版本，这可能是你的意图，也可能不是。 若要解决此问题，我们建议你提供不与其他本地名称冲突的局部变量名称。

## <a name="example"></a>示例

下面的示例生成 C4456，因为中的循环控制变量 `int x` 和局部变量 `double x` `member_fn` 具有相同的名称。 若要解决此问题，请对本地变量使用不同的名称。

```cpp
// C4456_hide.cpp
// compile with: cl /W4 /c C4456_hide.cpp

struct S {
    void member_fn(unsigned u) {
        double x = 0;
        for (int x = 0; x < 10; ++x) {  // C4456
            u += x; // uses local int x
        }
        x += u; // uses local double x
    }
} s;
```
