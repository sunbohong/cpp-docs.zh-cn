---
description: 了解详细信息： char_traits &lt; char32_t &gt; 结构
title: char_traits&lt;char32_t&gt; 结构
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::char_traits<char_32t>
- char_traits<char32_t>
helpviewer_keywords:
- char_traits<char32_t> class
ms.assetid: c0315466-45d0-4a99-b83e-3b1dbfbfbbc3
ms.openlocfilehash: 5b1b37421ef5e43c301cf36e1688806c8b6c8724
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325243"
---
# <a name="char_traitsltchar32_tgt-struct"></a>char_traits&lt;char32_t&gt; 结构

作为模板结构的专用化的结构，该 **结构 \<CharType> char_traits** 类型为的元素 **`char32_t`** 。

## <a name="syntax"></a>语法

```cpp
template <>
struct char_traits<char32_t>;
```

## <a name="remarks"></a>备注

专用化允许结构利用操作此类型对象的库函数 **`char32_t`** 。

## <a name="requirements"></a>要求

**标头：**\<string>

**命名空间:** std

## <a name="see-also"></a>请参阅

[\<string>](../standard-library/string.md)\
[char_traits 结构](../standard-library/char-traits-struct.md)
