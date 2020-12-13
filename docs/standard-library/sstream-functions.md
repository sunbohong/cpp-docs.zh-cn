---
description: 了解详细信息： &lt; m &gt; 函数
title: '&lt;sstream&gt; 函数'
ms.date: 11/04/2016
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: 81fd6f392ca1fde26cf150d8079650c748e670ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153832"
---
# <a name="ltsstreamgt-functions"></a>&lt;sstream&gt; 函数

[swap](#sstream_swap)

## <a name="swap"></a><a name="sstream_swap"></a> 购

交换两个 `sstream` 对象间的值。

```cpp
template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringbuf<Elem, Tr, Alloc>& left,
    basic_stringbuf<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_istringstream<Elem, Tr, Alloc>& left,
    basic_istringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_ostringstream<Elem, Tr, Alloc>& left,
    basic_ostringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringstream<Elem, Tr, Alloc>& left,
    basic_stringstream<Elem, Tr, Alloc>& right);
```

### <a name="parameters"></a>parameters

*左中*\
引用 `sstream` 对象。

*然后*\
引用 `sstream` 对象。

### <a name="remarks"></a>备注

该模板函数执行 `left.swap(right)`。

## <a name="see-also"></a>请参阅

[\<sstream>](../standard-library/sstream.md)
