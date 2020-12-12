---
description: 了解详细信息： char_traits &lt; wchar_t &gt; 结构
title: char_traits&lt;wchar_t&gt; 结构
ms.date: 11/04/2016
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
ms.openlocfilehash: 0276f4b50cb0039d0bec49b1b3eb2a0b3b2463aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325217"
---
# <a name="char_traitsltwchar_tgt-struct"></a>char_traits&lt;wchar_t&gt; 结构

一个类，该类是模板结构 **char_traits \<CharType>** 专用于类型的元素的 **`wchar_t`** 。

## <a name="syntax"></a>语法

```cpp
template <>
struct char_traits<wchar_t>;
```

## <a name="remarks"></a>备注

专用化允许结构利用操作此类型对象的库函数 **`wchar_t`** 。

## <a name="requirements"></a>要求

**标头：**\<string>

**命名空间:** std

## <a name="see-also"></a>请参阅

[char_traits 结构](../standard-library/char-traits-struct.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
