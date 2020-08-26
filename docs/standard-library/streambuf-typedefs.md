---
title: '&lt;streambuf&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: f08c08de0d6449714f953f5a65fadd2e0279ed44
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843191"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; typedef

[streambuf](#streambuf)\
[wstreambuf](#wstreambuf)

## <a name="streambuf"></a><a name="streambuf"></a> streambuf

`basic_streambuf`使用作为模板参数的的专用化 **`char`** 。

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>注解

类型是类模板 [basic_streambuf](../standard-library/basic-streambuf-class.md)的同义词，专用于 **`char`** 具有默认字符特征的类型的元素。

## <a name="wstreambuf"></a><a name="wstreambuf"></a> wstreambuf

`basic_streambuf`使用作为模板参数的的专用化 **`wchar_t`** 。

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>注解

类型是类模板 [basic_streambuf](../standard-library/basic-streambuf-class.md)的同义词，专用于 **`wchar_t`** 具有默认字符特征的类型的元素。

## <a name="see-also"></a>另请参阅

[\<streambuf>](../standard-library/streambuf.md)
