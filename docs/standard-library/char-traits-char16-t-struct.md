---
description: 了解详细信息： char_traits &lt; char16_t &gt; 结构
title: char_traits&lt;char16_t&gt; 结构
ms.date: 11/04/2016
f1_keywords:
- char_traits<char16_t>
- iosfwd/std::char_traits<char16_t>
helpviewer_keywords:
- char_traits<char16_t> class
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
ms.openlocfilehash: 2ad725b514d6804edfdea6d4ba72c2cfd44c4f21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325257"
---
# <a name="char_traitsltchar16_tgt-struct"></a>char_traits&lt;char16_t&gt; 结构

作为模板结构的专用化的结构，该 **结构 \<CharType> char_traits** 类型为的元素 **`char16_t`** 。

## <a name="syntax"></a>语法

```cpp
template <>
struct char_traits<char16_t>;
```

## <a name="remarks"></a>备注

专用化允许结构利用操作类型对象的库函数 **`char16_t`** 。

## <a name="requirements"></a>要求

**标头：**\<string>

**命名空间:** std

## <a name="see-also"></a>请参阅

[\<string>](../standard-library/string.md)\
[char_traits 结构](../standard-library/char-traits-struct.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
