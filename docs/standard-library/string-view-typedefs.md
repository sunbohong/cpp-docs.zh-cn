---
title: '&lt;string_view &gt; typedef'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: 2afaaea466cc3b1ca46d2acdf0ceb5a42c597743
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836125"
---
# <a name="ltstring_viewgt-typedefs"></a>&lt;string_view &gt; typedef

[string_view](#string_view)\
[u16string_view](#u16string_view)\
[u32string_view](#u32string_view)\
[wstring_view](#wstring_view)

## <a name="string_view"></a><a name="string_view"></a> string_view

一种类型，该类型描述与类型的元素 [basic_string_view](../standard-library/basic-string-view-class.md) 的类模板的专用化 **`char`** 。

```cpp
typedef basic_string_view<char, char_traits<char>> string_view;
```

### <a name="remarks"></a>注解

以下是等效声明：

```cpp
string_view str("Hello");

basic_string_view<char> str("Hello");
```

关于字符串构造函数的列表，请参阅 [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string)。

## <a name="u16string_view"></a><a name="u16string_view"></a> u16string_view

一种类型，该类型描述与类型的元素 [basic_string_view](../standard-library/basic-string-view-class.md) 的类模板的专用化 **`char16_t`** 。

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>注解

关于字符串构造函数的列表，请参阅 [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string)。

## <a name="u32string_view"></a><a name="u32string_view"></a> u32string_view

一种类型，该类型描述与类型的元素 [basic_string_view](../standard-library/basic-string-view-class.md) 的类模板的专用化 **`char32_t`** 。

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>注解

关于字符串构造函数的列表，请参阅 [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string)。

## <a name="wstring_view"></a><a name="wstring_view"></a> wstring_view

一种类型，该类型描述与类型的元素 [basic_string_view](../standard-library/basic-string-view-class.md) 的类模板的专用化 **`wchar_t`** 。

```cpp
typedef basic_string_view<wchar_t, char_traits<wchar_t>> wstring_view;
```

### <a name="remarks"></a>注解

以下是等效声明：

```cpp
wstring_view wstr(L"Hello");

basic_string_view<wchar_t> wstr(L"Hello");
```

关于字符串构造函数的列表，请参阅 [basic_string:: basic_string](../standard-library/basic-string-class.md#basic_string)。

> [!NOTE]
> 在 Windows 上，的大小 **`wchar_t`** 为两个字节，但对于所有平台，这并不一定是这种情况。 如果需要一个宽度为的 string_view 宽字符类型，并且保证在所有平台上保持不变，请使用 [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) 或 [u32string_view](../standard-library/string-view-typedefs.md#u32string_view)。

## <a name="see-also"></a>另请参阅

[\<string_view>](../standard-library/string-view.md)
