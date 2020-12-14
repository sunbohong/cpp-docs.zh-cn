---
description: 了解详细信息： is_signed 类
title: is_signed 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_signed
helpviewer_keywords:
- is_signed class
- is_signed
ms.assetid: 20ae44d9-22ad-4fbd-b26a-f18c62689451
ms.openlocfilehash: fefdf5e178bfbb5d2d77220ba51e36b2574606ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247678"
---
# <a name="is_signed-class"></a>is_signed 类

测试类型是否为带符号整数。

## <a name="syntax"></a>语法

```cpp
template <class Ty>
struct is_signed;
```

### <a name="parameters"></a>parameters

*Ty*\
要查询的类型。

## <a name="remarks"></a>备注

如果类型 *Ty* 是带符号整型类型或带符号整型类型，则类型谓词的实例为 true `cv-qualified` ; 否则为 false。

## <a name="example"></a>示例

```cpp
// std__type_traits__is_signed.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_signed<trivial> == " << std::boolalpha
        << std::is_signed<trivial>::value << std::endl;
    std::cout << "is_signed<int> == " << std::boolalpha
        << std::is_signed<int>::value << std::endl;
    std::cout << "is_signed<unsigned int> == " << std::boolalpha
        << std::is_signed<unsigned int>::value << std::endl;
    std::cout << "is_signed<float> == " << std::boolalpha
        << std::is_signed<float>::value << std::endl;

    return (0);
    }
```

```Output
is_signed<trivial> == false
is_signed<int> == true
is_signed<unsigned int> == false
is_signed<float> == true
```

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)\
[is_unsigned 类](../standard-library/is-unsigned-class.md)
