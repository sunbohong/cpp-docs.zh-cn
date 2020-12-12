---
description: 了解详细信息： equal_to 结构
title: equal_to 结构
ms.date: 11/04/2016
f1_keywords:
- functional/std::equal_to
helpviewer_keywords:
- equal_to function
- equal_to struct
ms.assetid: 8e4f2b50-b2db-48e3-b4cc-6cc03362c2a6
ms.openlocfilehash: cae0531c31396d16d447e3b0123dc679bbfd5aa6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324431"
---
# <a name="equal_to-struct"></a>equal_to 结构

一个二元谓词，该谓词对其参数 () 执行相等运算 `operator==` 。

## <a name="syntax"></a>语法

```cpp
template <class Type = void>
struct equal_to : public binary_function<Type, Type, bool>
{
    bool operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator==
template <>
struct equal_to<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
      ->  decltype(std::forward<T>(Left) == std::forward<U>(Right));
};
```

### <a name="parameters"></a>parameters

*Type*、 *T*、 *U*\
支持 `operator==` 接受指定或推断类型的操作数的任何类型。

*左中*\
相等运算的左操作数。 非专用化的模板 *采用类型为* 的左值引用参数。 专用模板完全转发推断类型 *T* 的左值和右值引用参数。

*然后*\
相等运算的右操作数。 非专用化的模板 *采用类型为* 的左值引用参数。 专用模板完全转发推断类型 *U* 的左值和右值引用参数。

## <a name="return-value"></a>返回值

`Left == Right` 的结果。 专专用化模板可完美转移结果，该结果具有由 `operator==` 返回的类型。

## <a name="remarks"></a>备注

类型 *类型的对象必须可* 比较相等性。 这要求在对象集上定义的 `operator==` 满足等价关系的数学性质。 所有内置的数字和指针类型都满足此要求。

## <a name="example"></a>示例

```cpp
// functional_equal_to.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <double> v1, v2, v3 ( 6 );
   vector <double>::iterator Iter1, Iter2, Iter3;

   int i;
   for ( i = 0 ; i <= 5 ; i+=2 )
   {
      v1.push_back( 2.0 *i );
      v1.push_back( 2.0 * i + 1.0 );
   }

   int j;
   for ( j = 0 ; j <= 5 ; j+=2 )
   {
      v2.push_back( - 2.0 * j );
      v2.push_back( 2.0 * j + 1.0 );
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Testing for the element-wise equality between v1 & v2
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),
      equal_to<double>( ) );

   cout << "The result of the element-wise equal_to comparison\n"
      << "between v1 & v2 is: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
```

```Output
The vector v1 = ( 0 1 4 5 8 9 )
The vector v2 = ( -0 1 -4 5 -8 9 )
The result of the element-wise equal_to comparison
between v1 & v2 is: ( 1 1 0 1 0 1 )
```
