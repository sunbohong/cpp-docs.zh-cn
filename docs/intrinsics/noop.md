---
description: 详细了解 Microsoft C/c + + 内部函数： __noop
title: __noop
ms.date: 12/16/2020
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 5fd300ca8d68305a12e6b5540be05aa60a042a44
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645080"
---
# `__noop`

**特定于 Microsoft** 的 **`__noop`** 内部函数指定应忽略某个函数。 参数列表已经过分析，但没有为参数生成任何代码。 编译器会将自变量视为编译器警告 C4100 和类似分析的用途。 内部函数用于 `__noop` 采用可变数量的自变量的全局调试函数。

编译器 **`__noop`** 在编译时将内部转换为0。

## <a name="example"></a>示例

下面的代码演示如何使用 **`__noop`** 。

```cpp
// compiler_intrinsics__noop.cpp
// compile using: cl /EHsc /W4 compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

#define IGNORE(x) { __noop(x); }

int main(int argv, char ** argc)
{
   IGNORE(argv);
   IGNORE(argc);
   PRINT("\nDEBUG is defined\n");
}
```

## <a name="see-also"></a>另请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[关键字](../cpp/keywords-cpp.md)
