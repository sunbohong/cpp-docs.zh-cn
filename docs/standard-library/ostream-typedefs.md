---
title: '&lt;ostream&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: ff9f19f56c8d8fdb9e469e6361a5419468fe7e67
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846402"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; typedefs

[ostream](#ostream)\
[wostream](#wostream)

## <a name="ostream"></a><a name="ostream"></a> ostream

从专用于 **`char`** 并专用于的 basic_ostream 创建一个类型 `char_traits` **`char`** 。

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>注解

类型是类模板 [basic_ostream](../standard-library/basic-ostream-class.md)的同义词，专用于 **`char`** 具有默认字符特征的类型的元素。

## <a name="wostream"></a><a name="wostream"></a> wostream

从专用于 **`wchar_t`** 并专用于的 basic_ostream 创建一个类型 `char_traits` **`wchar_t`** 。

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>注解

类型是类模板 [basic_ostream](../standard-library/basic-ostream-class.md)的同义词，专用于 **`wchar_t`** 具有默认字符特征的类型的元素。

## <a name="see-also"></a>另请参阅

[\<ostream>](../standard-library/ostream.md)
