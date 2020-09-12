---
title: '&lt;sstream&gt; 函数'
ms.date: 11/04/2016
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: 43fcffe12afe50a94f06a18e7ee06729bc85854e
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039893"
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

### <a name="parameters"></a>参数

*左中*\
引用 `sstream` 对象。

*然后*\
引用 `sstream` 对象。

### <a name="remarks"></a>备注

该模板函数执行 `left.swap(right)`。

## <a name="see-also"></a>另请参阅

[\<sstream>](../standard-library/sstream.md)
