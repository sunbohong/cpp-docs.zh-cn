---
description: 了解详细信息： unary_negate 类
title: unary_negate 类
ms.date: 02/21/2019
f1_keywords:
- functional/std::unary_negate
helpviewer_keywords:
- unary_negate class
ms.assetid: e3b86eec-3205-49b9-ab83-f55225af4e0c
ms.openlocfilehash: 33907bce7e03005488d23b3ac39666b6310b0e43
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207405"
---
# <a name="unary_negate-class"></a>unary_negate 类

提供成员函数的类模板，用于对指定一元函数的返回值求反。 在 c + + 17 中弃用，以支持 [not_fn](functional-functions.md#not_fn)。

## <a name="syntax"></a>语法

```cpp
template <class Predicate>
class unary_negate
    : public unaryFunction<typename Predicate::argument_type, bool>
{
    explicit unary_negate(const Predicate& Func);
    bool operator()(const typename Predicate::argument_type& left) const;
};
```

### <a name="parameters"></a>parameters

*求*\
要求反的一元函数。

*左中*\
要求反的一元函数的操作数。

## <a name="return-value"></a>返回值

一元函数的求反运算。

## <a name="remarks"></a>备注

类模板存储一元函数对象 *\_ Func* 的副本。 它将其成员函数定义 `operator()` 为返回 `!_Func(left)` 。

很少直接使用 `unary_negate` 的构造函数。 Helper 函数 [not1](../standard-library/functional-functions.md#not1) 可提供更简单的方法，用于声明和使用 **unary_negator** 适配器谓词。

## <a name="example"></a>示例

```cpp
// functional_unary_negate.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 7; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    // Count the elements greater than 10
    result1 = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    vector<int>::iterator::difference_type result2;
    // Use the negator to count the elements less than or equal to 10
    result2 = count_if(v1.begin(), v1.end(),
        unary_negate<binder2nd <greater<int> > >(bind2nd(greater<int>(),10)));

    // The following helper function not1 also works for the above line
    // not1(bind2nd(greater<int>(), 10)));

    cout << "The number of elements in v1 not greater than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 30 35 )
The number of elements in v1 greater than 10 is: 5.
The number of elements in v1 not greater than 10 is: 3.
```
