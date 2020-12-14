---
description: 了解详细信息： &lt; streambuf &gt; typedef
title: '&lt;streambuf&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: ae5394213143b05704d452e38eaae0b3581849cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221964"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; typedef

[streambuf](#streambuf)\
[wstreambuf](#wstreambuf)

## <a name="streambuf"></a><a name="streambuf"></a> streambuf

`basic_streambuf`使用作为模板参数的的专用化 **`char`** 。

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>备注

类型是类模板 [basic_streambuf](../standard-library/basic-streambuf-class.md)的同义词，专用于 **`char`** 具有默认字符特征的类型的元素。

## <a name="wstreambuf"></a><a name="wstreambuf"></a> wstreambuf

`basic_streambuf`使用作为模板参数的的专用化 **`wchar_t`** 。

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>备注

类型是类模板 [basic_streambuf](../standard-library/basic-streambuf-class.md)的同义词，专用于 **`wchar_t`** 具有默认字符特征的类型的元素。

## <a name="see-also"></a>请参阅

[\<streambuf>](../standard-library/streambuf.md)
