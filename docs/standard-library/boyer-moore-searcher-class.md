---
description: 了解详细信息： boyer_moore_searcher 类
title: boyer_moore_searcher 类
ms.date: 08/03/2019
f1_keywords:
- functional/std::boyer_moore_searcher
helpviewer_keywords:
- std::boyer_moore_searcher [C++]
ms.openlocfilehash: 7d8efe145870847aae8e961dad1b4a92fec8bd57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325406"
---
# <a name="boyer_moore_searcher-class"></a>boyer_moore_searcher 类

`boyer_moore_searcher`类是一个函数对象类型，该类型使用 Boyer-Moore 算法搜索在对象的构造函数中指定的序列。 搜索是在提供给对象的函数调用运算符的另一序列中完成的。 此类作为参数传递给 [std：： search](algorithm-functions.md#search)的重载之一。

## <a name="syntax"></a>语法

```cpp
template <
    class RandomAccessIterator1,
    class Hash = hash<typename iterator_traits<RandomAccessIterator1>::value_type>,
    class BinaryPredicate = equal_to<>>
class boyer_moore_searcher
{
    boyer_moore_searcher(
        RandomAccessIterator1 pat_first,
        RandomAccessIterator1 pat_last,
        Hash hf = Hash(),
        BinaryPredicate pred = BinaryPredicate());

    template <class RandomAccessIterator2>
    pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
        RandomAccessIterator2 first,
        RandomAccessIterator2 last) const;
};
```

## <a name="members"></a>成员

| 成员 | 描述 |
| - | - |
| **构造函数** | |
| [boyer_moore_searcher](#boyer-moore-searcher-constructor) | 构造一个搜索者实例。 |
| **运算符** | |
| [运算符 ( # B1 ](#operator-call) | 对序列调用操作。 |

## <a name="boyer_moore_searcher-constructor"></a><a name="boyer-moore-searcher-constructor"></a> boyer_moore_searcher 构造函数

`boyer_moore_searcher`使用序列搜索、哈希函数对象和相等谓词来构造函数对象。

```cpp
boyer_moore_searcher(
    RandomAccessIterator pat_first,
    RandomAccessIterator pat_last,
    Hash hf = Hash(),
    BinaryPredicate pred = BinaryPredicate());
```

### <a name="parameters"></a>parameters

*pat_first*\
要搜索的序列的初始元素。

*pat_last*\
要搜索的序列的末尾。

*hf*\
用于对序列元素进行哈希处理的可调用对象。

*pred*\
序列元素的可选相等比较谓词。 如果未指定相等比较类型，则默认值为 `std::equal_to` 。

### <a name="remarks"></a>备注

引发由 *BinaryPredicate*、 *Hash* 或 *RandomAccessIterator* 类型的复制构造函数或 *BinaryPredicate* 或 *Hash* 的调用运算符引发的任何异常。

此类是 c + + 17 中新增的。

## <a name="operator"></a><a name="operator-call"></a> 运算符 ( # A1

函数对象的调用运算符。 在参数序列内搜索 `[first, last)` 指定给构造函数的序列。

```cpp
template <class ForwardIterator2>
pair<RandomAccessIterator2, RandomAccessIterator2> operator()(
    RandomAccessIterator2 first,
    RandomAccessIterator2 last) const;
```

### <a name="parameters"></a>parameters

*1*\
要在其中进行搜索的序列的初始元素。

*时间*\
要在其中进行搜索的序列的末尾。

### <a name="remarks"></a>备注

如果搜索模式 `[pat_first, pat_last)` 为空，则返回 `make_pair(first, first)` 。 如果找不到搜索模式，则返回 `make_pair(last, last)` 。 否则，将返回一对迭代器，该迭代器指向中序列的开头和结尾，并 `[first, last)` `[pat_first, pat_last)` 根据谓词 *pred*。

此类是 c + + 17 中新增的。

## <a name="see-also"></a>请参阅

[\<functional>](functional.md)\
[算法函数](algorithm-functions.md)\
[boyer_moore_horspool_searcher 类](boyer-moore-horspool-searcher-class.md)\
[std：： search](algorithm-functions.md#search)
