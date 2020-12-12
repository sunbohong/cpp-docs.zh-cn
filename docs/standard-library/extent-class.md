---
description: 了解详细信息：区类
title: extent 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::extent
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
ms.openlocfilehash: d3db49db99d2cb7a241ca3b69c48fa6bcf2cb490
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324381"
---
# <a name="extent-class"></a>extent 类

获取数组维度。

## <a name="syntax"></a>语法

```cpp
template <class Ty, unsigned I = 0>
struct extent;
```

### <a name="parameters"></a>parameters

*Ty*\
要查询的类型。

*看到*\
绑定到查询的数组。

## <a name="remarks"></a>备注

如果 *Ty* 是至少具有 *i* 维的数组类型，则类型查询会保留 *i* 指定的维度中的元素数目。如果 *Ty* 不是数组类型或其秩小于 *I*，或者如果 *I* 为零且 *Ty* 的类型为 "未知绑定的数组 `U` "，则类型查询保留值0。

## <a name="example"></a>示例

```cpp
// std__type_traits__extent.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "extent 0 == "
        << std::extent<int[5][10]>::value << std::endl;
    std::cout << "extent 1 == "
        << std::extent<int[5][10], 1>::value << std::endl;

    return (0);
    }
```

```Output
extent 0 == 5
extent 1 == 10
```

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)\
[remove_all_extents 类](../standard-library/remove-all-extents-class.md)\
[remove_extent 类](../standard-library/remove-extent-class.md)
