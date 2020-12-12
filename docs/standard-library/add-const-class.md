---
description: 了解详细信息： add_const 类
title: add_const 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_const
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
ms.openlocfilehash: ce1dd895a5968234feca7905d3b9f8d571336053
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319939"
---
# <a name="add_const-class"></a>add_const 类

从类型设置常量类型。

## <a name="syntax"></a>语法

```cpp
template <class Ty>
struct add_const;
```

### <a name="parameters"></a>parameters

*Ty*\
要修改的类型。

## <a name="remarks"></a>备注

如果 *Ty* 是引用、函数或常量限定类型，则类型修饰符的实例会保留 *修改后的* 类型，否则为 `const Ty` 。

## <a name="example"></a>示例

```cpp
// std__type_traits__add_const.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
{
    std::add_const<int>::type *p = (const int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_const<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_const<int> == int
```

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](type-traits.md)\
[remove_const 类](remove-const-class.md)
