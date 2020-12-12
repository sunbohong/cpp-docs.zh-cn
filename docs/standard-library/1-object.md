---
description: 了解更多： _1 对象
title: _1 对象
ms.date: 11/04/2016
f1_keywords:
- _1
- std::_1
- functional/std::_1
helpviewer_keywords:
- _1 object
ms.assetid: 30c3c480-ff31-4708-94be-7d0d65f243c9
ms.openlocfilehash: dc081cff3fcb64826508dd9d2373b3eab219c82b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319952"
---
# <a name="_1-object"></a>_1 对象

可替换自变量的占位符。

## <a name="syntax"></a>语法

```cpp
namespace placeholders {
    extern unspecified _1, _2, ... _M
} // namespace placeholders (within std)
```

## <a name="remarks"></a>备注

对象 `_1, _2, ... _M` 是占位符，分别用于指定第一个、第二个 "..."、"Mth" 参数，以及对 [bind](functional-functions.md#bind)返回的对象的函数调用。 使用 `_N` 指定评估绑定表达式时第 N 个参数应插入的位置。

在此次实现中，`M` 的值为 20。

## <a name="example"></a>示例

```cpp
// std__functional_placeholder.cpp
// compile with: /EHsc
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std::placeholders;

void square(double x)
    {
    std::cout << x << "^2 == " << x * x << std::endl;
    }

void product(double x, double y)
    {
    std::cout << x << "*" << y << " == " << x * y << std::endl;
    }

int main()
    {
    double arg[] = {1, 2, 3};

    std::for_each(&arg[0], &arg[3], square);
    std::cout << std::endl;

    std::for_each(&arg[0], &arg[3], std::bind(product, _1, 2));
    std::cout << std::endl;

    std::for_each(&arg[0], &arg[3], std::bind(square, _1));

    return (0);
    }
```

```Output
1^2 == 1
2^2 == 4
3^2 == 9

1*2 == 2
2*2 == 4
3*2 == 6

1^2 == 1
2^2 == 4
3^2 == 9
```
