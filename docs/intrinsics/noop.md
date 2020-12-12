---
description: 了解详细信息： __noop
title: __noop
ms.date: 09/02/2019
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 4b140141e0f773f01cd666dd67f77244d7aef8a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222458"
---
# <a name="__noop"></a>__noop

**Microsoft 专用**

**`__noop`** 内部函数指定应忽略某个函数。 参数列表已经过分析，但没有为参数生成任何代码。 它旨在用于采用可变数量的参数的全局调试函数。

编译器 **`__noop`** 在编译时将内部转换为0。

## <a name="example"></a>示例

下面的代码演示如何使用 **`__noop`** 。

```cpp
// compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

int main() {
   PRINT("\nhello\n");
}
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)\
[关键字](../cpp/keywords-cpp.md)
