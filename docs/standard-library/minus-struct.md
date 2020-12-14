---
description: 了解详细信息：减号 Struct
title: minus 结构
ms.date: 11/04/2016
f1_keywords:
- functional/std::minus
helpviewer_keywords:
- minus struct
- minus class
ms.assetid: 7bce784e-2be6-413a-b516-004e9ecb2a39
ms.openlocfilehash: fe9fb343a49fb8097322b687326d3c986ba25ee5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230492"
---
# <a name="minus-struct"></a>minus 结构

对其自变量执行减法运算（二进制 `operator-`）的预定义函数对象。

## <a name="syntax"></a>语法

```
template <class Type = void>
struct minus : public binary_function <Type, Type, Type>
{
    Type operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator-
template <>
struct minus<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) - std::forward<U>(Right));
};
```

### <a name="parameters"></a>parameters

*Type*、 *T*、 *U*\
支持二元 `operator-` 接受指定或推断类型的操作数的类型。

*左中*\
运算的左操作数。 非专用化的模板 *采用类型为* 的左值引用参数。 专用模板完全转发推断类型 *T* 的左值和右值引用参数。

*然后*\
运算的右操作数。 非专用化的模板 *采用类型为* 的左值引用参数。 专用模板完全转发推断类型 *U* 的左值和右值引用参数。

## <a name="return-value"></a>返回值

`Left - Right` 的结果。 专用化模板可完美转移结果，该结果具有由 `operator-` 返回的类型。

## <a name="example"></a>示例

```cpp
// functional_minus.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <int> v1, v2, v3 ( 6 );
   vector <int>::iterator Iter1, Iter2, Iter3;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 4 * i + 1);
   }

   int j;
   for ( j = 0 ; j <= 5 ; j++ )
   {
      v2.push_back( 3 * j - 1);
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Finding the element-wise diference of the elements of v1 & v2
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),
      minus<int>( ) );

   cout << "The element-wise differences between v1 and v2 are: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
```

```Output
The vector v1 = ( 1 5 9 13 17 21 )
The vector v2 = ( -1 2 5 8 11 14 )
The element-wise differences between v1 and v2 are: ( 2 3 4 5 6 7 )
```
