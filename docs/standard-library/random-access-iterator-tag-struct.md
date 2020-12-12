---
description: 了解详细信息： random_access_iterator_tag 结构
title: random_access_iterator_tag 结构
ms.date: 11/04/2016
f1_keywords:
- xutility/std::random_access_iterator_tag
helpviewer_keywords:
- random_access_iterator_tag class
- random_access_iterator_tag struct
ms.assetid: 59f5b741-c5b4-459c-ad0a-3b67cddeea23
ms.openlocfilehash: 0186f451d5fbd98b8eebcd30fe469e75577954d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327552"
---
# <a name="random_access_iterator_tag-struct"></a>random_access_iterator_tag 结构

一个类，该类提供 `iterator_category` 表示随机访问迭代器的函数的返回类型。

## <a name="syntax"></a>语法

```cpp
struct random_access_iterator_tag    : public bidirectional_iterator_tag {};
```

## <a name="remarks"></a>备注

分类标记类用作算法选择的编译标记。 模板函数需要查找其迭代器参数的最特定的类别，以便可以在编译时使用最高效的算法。 对于每个 `Iterator` 类型的迭代器，`iterator_traits`< `Iterator`> **::iterator_category** 必须定义为最特定的类别标记，用于描述迭代器的行为。

此类型与 **iterator** \< **Iter**> **：： iterator_category** 在 `Iter` 描述可用作随机访问迭代器的对象时相同。

## <a name="example"></a>示例

```cpp
// iterator_rait.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>
#include <list>

using namespace std;

int main( )
{
   vector<int> vi;
   vector<char> vc;
   list<char> lc;
   iterator_traits<vector<int>:: iterator>::iterator_category cati;
   iterator_traits<vector<char>:: iterator>::iterator_category catc;
   iterator_traits<list<char>:: iterator>::iterator_category catlc;

   // These are both random-access iterators
   cout << "The type of iterator for vector<int> is "
       << "identified by the tag:\n "
       << typeid ( cati ).name( ) << endl;
   cout << "The type of iterator for vector<char> is "
       << "identified by the tag:\n "
       << typeid ( catc ).name( ) << endl;
   if ( typeid ( cati ) == typeid( catc ) )
      cout << "The iterators are the same." << endl << endl;
   else
      cout << "The iterators are not the same." << endl << endl;

   // But the list iterator is bidirectinal, not random access
   cout << "The type of iterator for list<char> is "
       << "identified by the tag:\n "
       << typeid (catlc).name( ) << endl;

   // cout << ( typeid ( vi.begin( ) ) == typeid( vc.begin( ) ) ) << endl;
   if ( typeid ( vi.begin( ) ) == typeid( vc.begin( ) ) )
      cout << "The iterators are the same." << endl;
   else
      cout << "The iterators are not the same." << endl;
   // A random-access iterator is a bidirectional iterator.
   cout << ( void* ) dynamic_cast< iterator_traits<list<char>:: iterator>
          ::iterator_category* > ( &catc ) << endl;
}
```

## <a name="sample-output"></a>示例输出

以下输出面向 x86。

```Output
The type of iterator for vector<int> is identified by the tag:
    struct std::random_access_iterator_tag
The type of iterator for vector<char> is identified by the tag:
    struct std::random_access_iterator_tag
The iterators are the same.

The type of iterator for list<char> is identified by the tag:
    struct std::bidirectional_iterator_tag
The iterators are not the same.
0012FF3B
```

## <a name="requirements"></a>要求

**标头：**\<iterator>

**命名空间:** std

## <a name="see-also"></a>请参阅

[bidirectional_iterator_tag 结构](../standard-library/bidirectional-iterator-tag-struct.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C + + 标准库参考](../standard-library/cpp-standard-library-reference.md)
