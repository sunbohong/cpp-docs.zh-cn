---
description: 详细了解：编译器警告 (等级 3) C4738
title: 编译器警告（等级 3）C4738
ms.date: 11/04/2016
f1_keywords:
- C4738
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
ms.openlocfilehash: d57b992438148b3925b5366747db0b9de53ec87e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332148"
---
# <a name="compiler-warning-level-3-c4738"></a>编译器警告（等级 3）C4738

将 32 位浮点型结果存储在内存中，可能会降低性能

C4738 警告，赋值、强制转换、传递的参数或其他操作的结果可能需要舍入，或者该操作用尽了寄存器，需要使用内存 (溢出) 。 这可能会导致性能下降。

若要解决此警告并避免进行舍入，请使用 [/fp： fast](../../build/reference/fp-specify-floating-point-behavior.md) 或 use **`double`** 而不是进行编译 **`float`** 。

若要解决此警告并避免超出寄存器运行，请更改计算的顺序并修改内联的使用

默认情况下，此警告处于关闭状态。 有关详细信息，请参阅 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)。

## <a name="example"></a>示例

下面的示例生成 C4738：

```cpp
// C4738.cpp
// compile with: /c /fp:precise /O2 /W3
// processor: x86
#include <stdio.h>

#pragma warning(default : 4738)

float func(float f)
{
    return f;
}

int main()
{
    extern float f, f1, f2;
    double d = 0.0;

    f1 = func(d);
    f2 = (float) d;
    f = f1 + f2;   // C4738
    printf_s("%f\n", f);
}
```
