---
description: 详细了解：编译器警告 (级别 4) C4840
title: 编译器警告 (等级 4) C4840
ms.date: 09/13/2018
f1_keywords:
- C4840
helpviewer_keywords:
- C4840
ms.openlocfilehash: a365dc38aff1ab9811407924f7f6e554d91c6f1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330469"
---
# <a name="compiler-warning-level-4-c4840"></a>编译器警告 (等级 4) C4840

> 类 "*type*" 作为可变参数函数的参数的不可移植使用

## <a name="remarks"></a>备注

传递给可变参数函数的类或结构必须是完全复制。 传递此类对象时，编译器只是执行按位复制，不会调用构造函数或析构函数。

从 Visual Studio 2017 开始提供此警告。

## <a name="example"></a>示例

下面的示例生成 C4840，并演示如何修复此问题：

```cpp
// C4840.cpp
// compile by using: cl /EHsc /W4 C4840.cpp
#include <stdio.h>

int main()
{
    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);

    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                       // as an argument to a variadic function
    // To correct the error, you can perform a static cast
    // to convert the object before passing it:
    printf("%i\n", static_cast<int>(s));
}
```

对于使用生成和管理的字符串 `CStringW` ，提供的 `operator LPCWSTR()` 应用于将对象强制转换 `CStringW` 为格式字符串所需的 C 样式字符串指针：

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```
