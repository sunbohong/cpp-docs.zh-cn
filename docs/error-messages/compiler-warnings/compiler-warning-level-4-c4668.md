---
description: 详细了解：编译器警告 (级别 4) C4668
title: 编译器警告（等级 4）C4668
ms.date: 11/04/2016
f1_keywords:
- C4668
helpviewer_keywords:
- C4668
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
ms.openlocfilehash: 559043027bf9fab38470223ea7735ca70297aabf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134051"
---
# <a name="compiler-warning-level-4-c4668"></a>编译器警告（等级 4）C4668

没有将“symbol”定义为预处理器宏，用“0”替换“directives”

未定义的符号与预处理器指令一起使用。 符号的计算结果将为 false。 若要定义符号，可以使用 [#define 指令](../../preprocessor/hash-define-directive-c-cpp.md) 或 [/d](../../build/reference/d-preprocessor-definitions.md) 编译器选项。

默认情况下，此警告处于关闭状态。 请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 了解详细信息。

## <a name="example"></a>示例

下面的示例生成 C4668：

```cpp
// C4668.cpp
// compile with: /W4
#include <stdio.h>

#pragma warning (default : 4668)   // turn warning on

int main()
{
    #if q   // C4668, q is not defined
        printf_s("defined");
    #else
        printf_s("undefined");
    #endif
}
```
