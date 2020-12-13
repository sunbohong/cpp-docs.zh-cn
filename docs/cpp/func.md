---
description: 了解有关以下方面的详细信息： __func__
title: __func__
ms.date: 10/19/2017
f1_keywords:
- __func__
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
ms.openlocfilehash: 6e075d0f566bb8c3eb72e62a30a36ef80528647b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337704"
---
# <a name="__func__"></a>__func__

**(c + + 11)** 预定义的标识符 &#95;&#95;func&#95;&#95; 被隐式定义为包含封闭函数的非限定和未修饰名称的字符串。 &#95;&#95;func&#95;&#95; 由 c + + 标准强制，并且不是 Microsoft 扩展。

## <a name="syntax"></a>语法

```cpp
__func__
```

## <a name="return-value"></a>返回值

返回一个以 null 结尾的 const char 字符数组，其中包含函数名称。

## <a name="example"></a>示例

```cpp
#include <string>
#include <iostream>

namespace Test
{
    struct Foo
    {
        static void DoSomething(int i, std::string s)
        {
           std::cout << __func__ << std::endl; // Output: DoSomething
        }
    };
}

int main()
{
    Test::Foo::DoSomething(42, "Hello");

    return 0;
}
```

## <a name="requirements"></a>要求

C++11
