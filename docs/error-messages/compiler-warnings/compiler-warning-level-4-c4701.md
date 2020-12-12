---
description: 详细了解：编译器警告 (级别 4) C4701
title: 编译器警告（等级 4）C4701
ms.date: 11/04/2016
f1_keywords:
- C4701
helpviewer_keywords:
- C4701
ms.assetid: d7c76c66-1f3f-4d3c-abe4-5d94c84a5a1f
ms.openlocfilehash: e09b368d3477459cf6eea053e1be2a50a429298c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133809"
---
# <a name="compiler-warning-level-4-c4701"></a>编译器警告（等级 4）C4701

使用了可能未初始化的局部变量 "name"

本地变量 *名称* 可能已被使用，但未分配值。 这可能导致不可预知的结果。

## <a name="example"></a>示例

以下代码生成了 C4701 和 C4703。

```cpp
#include <malloc.h>

void func(int size)
{
    void* p;
    if (size < 256) {
        p = malloc(size);
    }

    if (p != nullptr) // C4701 and C4703
        free(p);
}

int main()
{
    func(9);
}
```

```Output
c:\src\test.cpp(10) : warning C4701: potentially uninitialized local variable 'p' used
c:\src\test.cpp(10) : warning C4703: potentially uninitialized local pointer variable 'p' used
```

若要更正此警告，请初始化该变量，如以下示例所示：

```cpp
#include <malloc.h>

void func(int size)
{
    void* p = nullptr;
    if (size < 256) {
        p = malloc(size);
    }

    if (p != nullptr)
        free(p);
}

int main()
{
    func(9);
}
```

## <a name="see-also"></a>请参阅

[编译器警告 (等级 4) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)<br/>
[警告、/sdl 和改进未初始化的变量检测](https://www.microsoft.com/security/blog/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection/)
