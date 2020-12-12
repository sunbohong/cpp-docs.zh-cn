---
description: 了解详细信息： &lt; istream &gt; typedef
title: '&lt;istream&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: 576d1be7733a01689b4cfc511049dfad89390f63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277851"
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt; typedef

[iostream](#iostream)\
[istream](#istream)\
[wiostream](#wiostream)\
[wistream](#wistream)

## <a name="iostream"></a><a name="iostream"></a> iostream

专用化的类型 `basic_iostream` **`char`** 。

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>备注

类型是类模板 [basic_iostream](../standard-library/basic-iostream-class.md)的同义词，专用于 **`char`** 具有默认字符特征的类型的元素。

## <a name="istream"></a><a name="istream"></a> istream

专用化的类型 `basic_istream` **`char`** 。

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>备注

类型是类模板 [basic_istream](../standard-library/basic-istream-class.md)的同义词，专用于 **`char`** 具有默认字符特征的类型的元素。

## <a name="wiostream"></a><a name="wiostream"></a> wiostream

专用化的类型 `basic_iostream` **`wchar_t`** 。

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>备注

类型是类模板 [basic_iostream](../standard-library/basic-iostream-class.md)的同义词，专用于 **`wchar_t`** 具有默认字符特征的类型的元素。

## <a name="wistream"></a><a name="wistream"></a> wistream

专用化的类型 `basic_istream` **`wchar_t`** 。

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>备注

类型是类模板 [basic_istream](../standard-library/basic-istream-class.md)的同义词，专用于 **`wchar_t`** 具有默认字符特征的类型的元素。

## <a name="see-also"></a>请参阅

[\<istream>](../standard-library/istream.md)
