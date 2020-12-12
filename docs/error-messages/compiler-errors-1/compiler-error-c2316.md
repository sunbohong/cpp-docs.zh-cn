---
description: 了解更多：编译器错误 C2316
title: 编译器错误 C2316
ms.date: 07/08/2019
f1_keywords:
- C2316
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
ms.openlocfilehash: 0e2f528b3f13964a971b88fca110980947bd7d11
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282191"
---
# <a name="compiler-error-c2316"></a>编译器错误 C2316

> "*class_type*"：无法捕获，因为析构函数和/或复制构造函数不可访问或已被删除

通过值或引用捕获了异常，但复制构造函数和/或赋值运算符无法访问。

## <a name="remarks"></a>备注

Visual Studio 2015 中的一致性更改使得此错误适用于从派生的 MFC 异常的错误 catch 语句 `CException` 。 由于 `CException` 具有继承的私有复制构造函数，因此类及其派生类不复制，并且无法通过值传递，这也意味着无法通过值捕获它们。 通过值捕获 MFC 异常的 Catch 语句以前导致运行时出现未捕获的异常。 现在，编译器会正确地识别此情况并报告错误 C2316。 若要解决此问题，我们建议使用 MFC TRY/CATCH 宏，而不是编写自己的异常处理程序。 如果不适合您的代码，请改为按引用捕获 MFC 异常。

## <a name="example"></a>示例

下面的示例生成 C2316，并演示如何修复此问题：

```cpp
// C2316.cpp
// compile with: /EHsc
#include <stdio.h>

struct B
{
public:
    B() {}
    // Delete the following line to resolve.
private:
    // copy constructor
    B(const B&) {}
};

void f(const B&)
{
}

int main()
{
    try
    {
        B aB;
        f(aB);
    }
    catch (B b)    // C2316
    {
        printf_s("Caught an exception!\n");
    }
}
```
