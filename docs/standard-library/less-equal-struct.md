---
description: 了解详细信息： less_equal 结构
title: less_equal 结构
ms.date: 11/04/2016
f1_keywords:
- functional/std::less_equal
helpviewer_keywords:
- less_equal function
- less_equal struct
ms.assetid: 32085782-c7e0-4310-9b40-8aa3c1bff211
ms.openlocfilehash: b2d715971c5278629a6ea812c5a9c199f00c4a07
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312886"
---
# <a name="less_equal-struct"></a>less_equal 结构

一个二元谓词，该谓词对其参数执行 () 的小于或等于运算 `operator<=` 。

## <a name="syntax"></a>语法

```cpp
template <class Type = void>
struct less_equal : public binary_function <Type, Type, bool>
{
    bool operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator<=
template <>
struct less_equal<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const
    -> decltype(std::forward<T>(Left) <= std::forward<U>(Right));
};
```

### <a name="parameters"></a>parameters

*Type*、 *T*、 *U*\
支持 `operator<=` 接受指定或推断类型的操作数的任何类型。

*左中*\
小于或等于运算的左操作数。 非专用化的模板 *采用类型为* 的左值引用参数。 专用模板完全转发推断类型 *T* 的左值和右值引用参数。

*然后*\
小于或等于运算的右操作数。 非专用化的模板 *采用类型为* 的左值引用参数。 专用模板完全转发推断类型 *U* 的左值和右值引用参数。

## <a name="return-value"></a>返回值

`Left <= Right` 的结果。 专用化模板可完美转移结果，该结果具有由 `operator<=` 返回的类型。

## <a name="remarks"></a>备注

`less_equal` < `Type` 当且仅当此类型满足标准数学要求以便进行排序时，二进制谓词> 提供一组类型为 *type* 类型的元素值到等效类的严格弱排序。 任何指针类型的专用化都会产生元素的全序，所有不同值的元素都会相对于彼此进行排序。

## <a name="example"></a>示例

```cpp
// functional_less_equal.cpp
// compile with: /EHsc
#define _CRT_RAND_S
#include <stdlib.h>
#include <vector>
#include <algorithm>
#include <functional>
#include <cstdlib>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;
   vector <int>::reverse_iterator rIter1;
   unsigned int randomNumber;

   int i;
   for ( i = 0 ; i < 5 ; i++ )
   {
      if ( rand_s( &randomNumber ) == 0 )
      {
         // Convert the random number to be between 1 - 50000
         // This is done for readability purposes
         randomNumber = ( unsigned int) ((double)randomNumber /
            (double) UINT_MAX * 50000) + 1;

         v1.push_back( randomNumber );
      }
   }
   for ( i = 0 ; i < 3 ; i++ )
   {
      v1.push_back( 2836 );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   // use the binary predicate less_equal<int>( )
   sort( v1.begin( ), v1.end( ), less_equal<int>( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = (31247 37154 48755 15251 6205 2836 2836 2836)
Sorted vector v1 = (2836 2836 2836 6205 15251 31247 37154 48755)
```
