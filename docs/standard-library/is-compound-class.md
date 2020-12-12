---
description: 了解详细信息： is_compound 类
title: is_compound 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_compound
helpviewer_keywords:
- is_compound class
- is_compound
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
ms.openlocfilehash: 0bdd1b2f8c7ab827d9bed1025e30140244381c3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323825"
---
# <a name="is_compound-class"></a>is_compound 类

测试指定的类型是否为基本类型。

## <a name="syntax"></a>语法

```cpp
template <class Ty>
struct is_compound;
```

### <a name="parameters"></a>parameters

*Ty*\
要查询的类型。

## <a name="remarks"></a>备注

**`false`** 如果 *Ty* 的类型为基础类型，则类型谓词的实例将保留 (也就是说，如果 [is_fundamental](../standard-library/is-fundamental-class.md) \<Ty> 包含) ，则为 **`true`** ; 否则为 **`true`** 。 因此， **`true`** 如果 *Ty* 是数组类型、函数类型、指向 **`void`** 或对象或函数的指针、引用、类、联合、枚举或指向非静态类成员的指针或其中一类成员的 *cv 限定* 形式，则谓词保留。

## <a name="example"></a>示例

```cpp
// std__type_traits__is_compound.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_compound<trivial> == " << std::boolalpha
        << std::is_compound<trivial>::value << std::endl;
    std::cout << "is_compound<int[]> == " << std::boolalpha
        << std::is_compound<int[]>::value << std::endl;
    std::cout << "is_compound<int()> == " << std::boolalpha
        << std::is_compound<int()>::value << std::endl;
    std::cout << "is_compound<int&> == " << std::boolalpha
        << std::is_compound<int&>::value << std::endl;
    std::cout << "is_compound<void *> == " << std::boolalpha
        << std::is_compound<void *>::value << std::endl;
    std::cout << "is_compound<int> == " << std::boolalpha
        << std::is_compound<int>::value << std::endl;

    return (0);
    }
```

```Output
is_compound<trivial> == true
is_compound<int[]> == true
is_compound<int()> == true
is_compound<int&> == true
is_compound<void *> == true
is_compound<int> == false
```

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)\
[is_class 类](../standard-library/is-class-class.md)
