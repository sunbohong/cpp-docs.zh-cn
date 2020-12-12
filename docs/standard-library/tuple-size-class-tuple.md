---
description: 了解详细信息： tuple_size 类;
title: tuple_size 类
ms.date: 11/04/2016
f1_keywords:
- tuple_size
- std::tuple_size
- utility/std::tuple_size
helpviewer_keywords:
- std::tuple_size
ms.assetid: 73852fc5-eb68-41f1-8379-465cedc2314a
ms.openlocfilehash: e825acc02e27a8d0c1ae29e5bfcf4ac1e0a708b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168873"
---
# <a name="tuple_size-class"></a>tuple_size 类

包含 `tuple` 包含的元素数目。

## <a name="syntax"></a>语法

```cpp
// TEMPLATE STRUCT tuple_size
template <class Tuple>
   struct tuple_size;

// number of elements in array
template <class Elem, size_t Size>
   struct tuple_size<array<Elem, Size>>
      : integral_constant<size_t, Size>;

// size of pair
template <class T1, class T2>
   struct tuple_size<pair<T1, T2>>
      : integral_constant<size_t, 2>

// size of tuple
template <class... Types>
   struct tuple_size<tuple<Types...>>
      : integral_constant<size_t, sizeof...(Types)>;

// size of const tuple
template <class Tuple>
   struct tuple_size<const Tuple>;

// size of volatile tuple
template <class Tuple>
   struct tuple_size<volatile Tuple>;

// size of const volatile tuple
template <class Tuple>
   struct tuple_size<const volatile Tuple>;
```

```cpp
template <class T> inline constexpr size_t tuple_size_v = tuple_size<T>::value;
```

### <a name="parameters"></a>parameters

*聚合*\
元组的类型。

*Elem*\
数组元素的类型。

*规格*\
数组大小。

*T1*\
对的第一个成员的类型。

\
对的第二个成员的类型。

*各种*\
元组元素的类型。

## <a name="remarks"></a>备注

类模板具有一个成员 `value` ，该成员是一个整型常数表达式，其值是元组类型 *元组* 的范围。

数组的模板特殊化具有成员 `value` ，该成员是值为 *size*（数组大小）的整数常量表达式。

对的模板专用化拥有成员 `value`，它是整型常数表达式，值为 2。

## <a name="example"></a>示例

```cpp
#include <tuple>
#include <iostream>

using namespace std;

typedef tuple<int, double, int, double> MyTuple;
int main()
{
    MyTuple c0(0, 1.5, 2, 3.7);

    // display contents "0 1 2 3"
    cout << get<0>(c0);
    cout << " " << get<1>(c0);
    cout << " " << get<2>(c0);
    cout << " " << get<3>(c0) << endl;

    // display size "4"
    cout << " " << tuple_size<MyTuple>::value << endl;
}
```

```Output
0 1.5 2 3.7
4
```

## <a name="requirements"></a>要求

**标头：**\<tuple>

**标头：** \<array> 数组专用化的 () 

**标头：** \<utility> 对专用化的 () 

**命名空间:** std
