---
description: 了解详细信息： mask_array 类
title: mask_array 类
ms.date: 11/04/2016
f1_keywords:
- valarray/std::mask_array
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
ms.openlocfilehash: d3eb105c7779ff54ddbec3d68a518dc74d089903
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149352"
---
# <a name="mask_array-class"></a>mask_array 类

一个内部的辅助类模板，它通过提供子集数组之间的操作来支持作为父 valarray 的子集的对象（使用布尔表达式指定）。

## <a name="syntax"></a>语法

## <a name="remarks"></a>备注

此类描述一个对象，该对象存储对类 valarray 的对象的引用以及 `va` [](../standard-library/valarray-class.md) **\<Type>** `ba` 类 [ \<bool> valarray](../standard-library/valarray-bool-class.md)的对象，该对象描述要从对象中选择的元素的序列 `valarray<Type>` 。

您 `mask_array<Type>` 只能通过编写一个形式为 [va&#91;ba&#93;](../standard-library/valarray-class.md#op_at)的表达式来构造对象。 类 mask_array 的成员函数的行为类似于为定义的对应函数签名 `valarray<Type>` ，只不过只影响选定元素的序列。

序列最多包含个 `ba.size` 元素。 仅当 **ba**[ *J*] 为 true 时，才包括元素 *J* 。 因此，序列中的元素数量与中的 true 元素相同 `ba` 。 如果 `I` 是中最低 true 元素的索引 `ba` ，则 **va**[] 在 `I` 选定序列中为元素零。

## <a name="example"></a>示例

```cpp
// mask_array.cpp
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

   // Use masked subsets to assign a value of 10
   // to all elements grrater than 3 in value
   va [va > 3 ] = 10;
   cout << "The modified operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>输出

```Output
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 2 -1 10 -1 10 -1 10 -1).
```

## <a name="requirements"></a>要求

**标头：**\<valarray>

**命名空间:** std

## <a name="see-also"></a>请参阅

[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
