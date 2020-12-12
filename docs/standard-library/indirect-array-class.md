---
description: 了解详细信息： indirect_array 类
title: indirect_array 类
ms.date: 11/04/2016
f1_keywords:
- valarray/std::indirect_array
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
ms.openlocfilehash: 47c9a0e604fd9873d7705f70624e67d9b3a22a7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324036"
---
# <a name="indirect_array-class"></a>indirect_array 类

一个内部的辅助类模板，它通过在通过指定父级 valarray 的索引子集定义的子集数组间提供操作来支持作为 valarray 子集的对象。

## <a name="syntax"></a>语法

## <a name="remarks"></a>备注

此类描述一个对象，该对象存储对类 valarray 的对象的引用以及 `va` 类的 [](../standard-library/valarray-class.md) **\<Type>** 对象 `xa` ，该类 `valarray<size_t>` 描述要从对象中选择的元素的序列 `valarray<Type>` 。

`indirect_array<Type>`仅通过编写窗体的表达式来构造对象 `va[xa]` 。 类 indirect_array 的成员函数的行为类似于为定义的对应函数签名 `valarray<Type>` ，只不过只影响选定元素的序列。

序列由 xa 组成 **。**[size](../standard-library/valarray-class.md#size) 元素，其中元素 `I` 成为中的索引 **xa**[ `I` ] `va` 。

## <a name="example"></a>示例：

```cpp
// indirect_array.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      va [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 2 )
      va [ i ] =  -1;

   cout << "The initial operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   // Select 2nd, 4th & 6th elements
   // and assign a value of 10 to them
   valarray<size_t> indx ( 3 );
   indx [0] = 2;
   indx [1] = 4;
   indx [2] = 6;
   va[indx] = 10;

   cout << "The modified operand valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>输出

```cpp
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 10 -1 10 -1 10 -1 8 -1).
```

## <a name="requirements"></a>要求

**标头：**\<valarray>

**命名空间:** std

## <a name="see-also"></a>请参阅

[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
