---
description: 了解详细信息：相除结构
title: divides 结构
ms.date: 11/04/2016
f1_keywords:
- functional/std::divides
helpviewer_keywords:
- divides struct
- divides class
ms.assetid: b9cf8e9c-6981-43a6-a6a3-8f761987dd7a
ms.openlocfilehash: eae6054ea485a05747f8e282849b1fe282a89439
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232741"
---
# <a name="divides-struct"></a>divides 结构

一个预定义的函数对象，它对其参数 () 执行除法运算 `operator/` 。

## <a name="syntax"></a>语法

```cpp
template <class Type = void>
struct divides : public binary_function <Type, Type, Type>
{
    Type operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator/
template <>
struct divides<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const
    -> decltype(std::forward<T>(Left)*/ std::forward<U>(Right));
};
```

### <a name="parameters"></a>parameters

*Type*、 *T*、 *U*\
支持 `operator/` 接受指定或推断类型的操作数的类型。

*左中*\
除法运算的左操作数。 非专用化的模板 *采用类型为* 的左值引用参数。 专用模板完全转发推断类型 *T* 的左值和右值引用参数。

*然后*\
除法运算的右操作数。 非专用化的模板 *采用类型为* 的左值引用参数。 专用模板完全转发推断类型 *U* 的左值和右值引用参数。

## <a name="return-value"></a>返回值

`Left / Right` 的结果。 专专用化模板可完美转移结果，该结果具有由 `operator/` 返回的类型。

## <a name="example"></a>示例

```cpp
// functional_divides.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <double> v1, v2, v3 (6);
   vector <double>::iterator Iter1, Iter2, Iter3;

   int i;
   for ( i = 0 ; i <= 5 ; i++ )
   {
      v1.push_back( 7.0 * i );
   }

   int j;
   for ( j = 1 ; j <= 6 ; j++ )
   {
      v2.push_back( 2.0 * j);
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Finding the element-wise quotients of the elements of v1 & v2
   transform ( v1.begin( ), v1.end( ), v2.begin( ), v3.begin ( ),
      divides<double>( ) );

   cout << "The element-wise quotients are: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
```

```Output
The vector v1 = ( 0 7 14 21 28 35 )
The vector v2 = ( 2 4 6 8 10 12 )
The element-wise quotients are: ( 0 1.75 2.33333 2.625 2.8 2.91667 )
```
