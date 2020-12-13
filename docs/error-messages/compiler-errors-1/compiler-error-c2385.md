---
description: 了解更多：编译器错误 C2385
title: 编译器错误 C2385
ms.date: 11/04/2016
f1_keywords:
- C2385
helpviewer_keywords:
- C2385
ms.assetid: 6d3dd1f2-e56d-49d7-865c-6a9acdb17417
ms.openlocfilehash: 7978af162045d52e187e41999c55dcad716baeb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185903"
---
# <a name="compiler-error-c2385"></a>编译器错误 C2385

对 "member" 的访问不明确

成员可以从多个对象派生 (它继承自多个) 的对象。  若要解决此错误，

- 提供强制转换，使成员明确。

- 重命名基类中的不明确成员。

## <a name="example"></a>示例

下面的示例生成 C2385。

```cpp
// C2385.cpp
// C2385 expected
#include <stdio.h>

struct A
{
    void x(int i)
    {
        printf_s("\nIn A::x");
    }
};

struct B
{
    void x(char c)
    {
        printf_s("\nIn B::x");
    }
};

// Delete the following line to resolve.
struct C : A, B {}

// Uncomment the following 4 lines to resolve.
// struct C : A, B
// {
//     using B::x;
//     using A::x;
// };

int main()
{
    C aC;
    aC.x(100);
    aC.x('c');
}

struct C : A, B
{
    using B::x;
    using A::x;
};
```
