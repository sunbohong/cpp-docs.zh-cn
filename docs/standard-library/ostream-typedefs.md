---
description: 了解详细信息： &lt; ostream &gt; typedef
title: '&lt;ostream&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 886fb729f389fac161e4d154e00898b530d1d9f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193014"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; typedefs

[ostream](#ostream)\
[wostream](#wostream)

## <a name="ostream"></a><a name="ostream"></a> ostream

从专用于 **`char`** 并专用于的 basic_ostream 创建一个类型 `char_traits` **`char`** 。

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>备注

类型是类模板 [basic_ostream](../standard-library/basic-ostream-class.md)的同义词，专用于 **`char`** 具有默认字符特征的类型的元素。

## <a name="wostream"></a><a name="wostream"></a> wostream

从专用于 **`wchar_t`** 并专用于的 basic_ostream 创建一个类型 `char_traits` **`wchar_t`** 。

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>备注

类型是类模板 [basic_ostream](../standard-library/basic-ostream-class.md)的同义词，专用于 **`wchar_t`** 具有默认字符特征的类型的元素。

## <a name="see-also"></a>请参阅

[\<ostream>](../standard-library/ostream.md)
