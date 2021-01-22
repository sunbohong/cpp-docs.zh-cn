---
title: '&lt;string_view &gt; 运算符'
description: '`string_view`用于比较两个对象的运算符的 API 参考， `string_view` 或一个 `string_view` 其他字符串对象'
ms.date: 01/15/2021
f1_keywords:
- xstring/basic_string_view::operator!=
- xstring/basic_string_view::operator&gt;
- xstring/basic_string_view::operator&gt;=
- xstring/basic_string_view::operator&lt;
- xstring/basic_string_view::operator&lt;&lt;
- xstring/basic_string_view::operator&lt;=
- xstring/basic_string_view::operator+
- xstring/basic_string_view::operator==
- xstring/std::literals::string_view_literals::operator "sv
- std::literals::string_view_literals::operator sv
- std::literals::string_view_literals
- string_view_literals
helpviewer_keywords:
- std::basic_string_view::operator!=
- std::basic_string_view::operator&gt;
- std::basic_string_view::operator&gt;=
- std::basic_string_view::operator&lt;
- std::basic_string_view::operator&lt;&lt;
- std::basic_string_view::operator&lt;=, std::basic_string_view::operator==
ms.openlocfilehash: a14d82dc0b29f88cb25f5b24f0836f033d2b828e
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666896"
---
# <a name="string_view-operators"></a>`<string_view>` 运算符

使用这些运算符来比较两个 `string_view` 对象，或者 `string_view` 和一个其他字符串对象 (例如 [`std::string`](basic-string-class.md) ，或 `char*` 为其提供了隐式转换的) 。

[`operator!=`](#op_neq)\
[`operator>`](#op_gt)\
[`operator>=`](#op_gt_eq)\
[`operator<`](#op_lt)\
[`operator<<`](#op_lt_lt)\
[`operator<=`](#op_lt_eq)\
[`operator==`](#op_eq_eq)\
[`operator""sv`](#op_sv)

## <a name="operator"></a><a name="op_neq"></a> `operator!=`

测试运算符左侧的对象是否不等于右侧的对象。

```cpp
template <class CharType, class Traits>
bool operator!=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator!=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator!=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>参数

*左中*\
任何可转换的字符串类型或要比较的类型的对象 `basic_string_view` 。

*然后*\
任何可转换的字符串类型或要比较的类型的对象 `basic_string_view` 。

### <a name="return-value"></a>返回值

**`true`** 如果运算符左侧的对象不按字典顺序等于右侧的对象，则为; 否则为。否则为 **`false`** 。

### <a name="remarks"></a>注解

在另一侧，隐式转换必须从 *convertible_string_type* 到的 `string_view` 。

比较基于对字符序列进行成对字典比较。 如果它们具有相同数量的元素，并且元素都相等，则这两个对象相等。 否则，它们不相等。

## <a name="operator"></a><a name="op_eq_eq"></a> `operator==`

测试运算符左侧的对象是否等于右侧的对象。

```cpp
template <class CharType, class Traits>
bool operator==(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator==(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator==(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>参数

*左中*\
任何可转换的字符串类型或要比较的类型的对象 `basic_string_view` 。

*然后*\
任何可转换的字符串类型或要比较的类型的对象 `basic_string_view` 。

### <a name="return-value"></a>返回值

**`true`** 如果运算符左侧的对象按字典顺序等于右侧的对象，则为; 否则为。否则为 **`false`** 。

### <a name="remarks"></a>注解

在另一侧，隐式转换必须从 *convertible_string_type* 到的 `string_view` 。

比较基于对字符序列进行成对字典比较。 如果它们具有相同数量的元素，并且元素都相等，则这两个对象相等。

## <a name="operator"></a><a name="op_lt"></a> `operator<`

测试运算符左侧的对象是否小于右侧的对象。

```cpp
template <class CharType, class Traits>
bool operator<(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator<(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator<(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>参数

*左中*\
任何可转换的字符串类型或要比较的类型的对象 `basic_string_view` 。

*然后*\
任何可转换的字符串类型或要比较的类型的对象 `basic_string_view` 。

### <a name="return-value"></a>返回值

**`true`** 如果运算符左侧的对象按字典顺序小于右侧的对象，则为; 否则为。否则为 **`false`** 。

### <a name="remarks"></a>注解

从 *convertible_string_type* 到另一侧的 string_view 必须存在隐式转换。

比较基于对字符序列进行成对字典比较。 当遇到第一对不相等的字符时，将返回该比较的结果。 如果未找到不相等的字符，但一个序列较短，则较短的序列小于较长的序列。 换句话说，"cat" 小于 "猫"。

### <a name="example"></a>示例

```cpp
#include <string>
#include <string_view>

using namespace std;

int main()
{
    string_view sv1 { "ABA" };
    string_view sv2{ "ABAC" };
    string_view sv3{ "ABAD" };
    string_view sv4{ "ABACE" };

    bool result = sv2 > sv1; // true
    result = sv3 > sv2; // true
    result = sv3 != sv1; // true
    result = sv4 < sv3; // true because `C` < `D`
}
```

## <a name="operator"></a><a name="op_lt_eq"></a> `operator<=`

测试运算符左侧的对象是否小于或等于右侧的对象。

```cpp
template <class CharType, class Traits>
bool operator<=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator<=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator<=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>参数

*左中*\
任何可转换的字符串类型或要比较的类型的对象 `basic_string_view` 。

*然后*\
任何可转换的字符串类型或要比较的类型的对象 `basic_string_view` 。

### <a name="return-value"></a>返回值

**`true`** 如果运算符左侧的对象按字典顺序小于或等于右侧的对象，则为; 否则为。否则为 **`false`** 。

### <a name="remarks"></a>注解

请参阅 [`operator<`](#op_lt)。

## <a name="operator"></a><a name="op_lt_lt"></a> `operator<<`

将写入 `string_view` 到输出流中。

```cpp
template <class CharType, class Traits>
inline basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& Ostr, const basic_string_view<CharType, Traits> Str);
```

### <a name="parameters"></a>参数

*`Ostr`*\
要写入的输出流。

*`Str`*\
要输入到输出流中的 string_view。

### <a name="return-value"></a>返回值

要写入的输出流。

### <a name="remarks"></a>注解

使用此运算符将的内容插入 `string_view` 到输出流中，例如使用 [`std::cout`](iostream.md#cout) 。

## <a name="operator"></a><a name="op_gt"></a> `operator>`

测试运算符左侧的对象是否大于右侧的对象。

```cpp
template <class CharType, class Traits>
bool operator>(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator>(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator>(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>参数

*左中*\
任何可转换的字符串类型或要比较的类型的对象 `basic_string_view` 。

*然后*\
任何可转换的字符串类型或要比较的类型的对象 `basic_string_view` 。

### <a name="return-value"></a>返回值

**`true`** 如果运算符左侧的对象按字典顺序大于 `string_view` 右侧的对象，则为; 否则为 **`false`** 。

### <a name="remarks"></a>注解

请参阅 [`operator<`](#op_lt)。

## <a name="operator"></a><a name="op_gt_eq"></a> `operator>=`

测试运算符左侧的对象是否大于或等于右侧的对象。

```cpp
template <class CharType, class Traits>
bool operator>=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator>=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator>=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>参数

*`left`*\
任何可转换的字符串类型或要比较的类型的对象 `basic_string_view` 。

*`right`*\
任何可转换的字符串类型或要比较的类型的对象 `basic_string_view` 。

### <a name="return-value"></a>返回值

**`true`** 如果运算符左侧的对象按字典顺序大于或等于右侧的对象，则为; 否则为。否则为 **`false`** 。

### <a name="remarks"></a>注解

请参阅 [`operator<`](#op_lt)。

## <a name="operator-sv-string_view-literal"></a><a name="op_sv"></a>`operator"" sv` (`string_view` 文字) 

`string_view`从字符串文本构造。 需要命名空间 `std::literals::string_view_literals` 。

### <a name="example"></a>示例

```cpp

using namespace std;
using namespace literals::string_view_literals;

    string_view sv{ "Hello"sv };
    wstring_view wsv{ L"Hello"sv };
    u16string_view sv16{ u"Hello"sv };
    u32string_view sv32{ U"Hello"sv };
```

## <a name="requirements"></a>要求

[`/std:c++17`](../build/reference/std-specify-language-standard-version.md)

## <a name="see-also"></a>另请参阅

[`<string_view>`](../standard-library/string-view.md)
