---
title: '`codecvt` 类'
description: 描述 Microsoft C 运行时 `codecvt` 类 API
ms.date: 11/09/2020
f1_keywords:
- xlocale/std::codecvt
- xlocale/std::codecvt::extern_type
- xlocale/std::codecvt::intern_type
- xlocale/std::codecvt::state_type
- xlocale/std::codecvt::always_noconv
- xlocale/std::codecvt::do_always_noconv
- xlocale/std::codecvt::do_encoding
- xlocale/std::codecvt::do_in
- xlocale/std::codecvt::do_length
- xlocale/std::codecvt::do_max_length
- xlocale/std::codecvt::do_out
- xlocale/std::codecvt::do_unshift
- xlocale/std::codecvt::encoding
- xlocale/std::codecvt::in
- xlocale/std::codecvt::length
- xlocale/std::codecvt::max_length
- xlocale/std::codecvt::out
- xlocale/std::codecvt::unshift
helpviewer_keywords:
- std::codecvt [C++]
- std::codecvt [C++], extern_type
- std::codecvt [C++], intern_type
- std::codecvt [C++], state_type
- std::codecvt [C++], always_noconv
- std::codecvt [C++], do_always_noconv
- std::codecvt [C++], do_encoding
- std::codecvt [C++], do_in
- std::codecvt [C++], do_length
- std::codecvt [C++], do_max_length
- std::codecvt [C++], do_out
- std::codecvt [C++], do_unshift
- std::codecvt [C++], encoding
- std::codecvt [C++], in
- std::codecvt [C++], length
- std::codecvt [C++], max_length
- std::codecvt [C++], out
- std::codecvt [C++], unshift
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
ms.openlocfilehash: 8d2970297cca199c70c101dca93f453c512317c4
ms.sourcegitcommit: b38485bb3a9d479e0c5d64ffc3d841fa2c2b366f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441276"
---
# <a name="codecvt-class"></a>`codecvt` 类

描述可用作区域设置 facet 的对象的类模板。 它可以控制用于对程序中的字符进行编码的值序列与用于对程序外的字符进行编码的值序列之间的转换。

## <a name="syntax"></a>语法

```cpp
template <class CharType, class Byte, class StateType>
class codecvt : public locale::facet, codecvt_base;
```

### <a name="parameters"></a>参数

*`CharType`*\
在程序中用于对字符进行编码的类型。

*`Byte`*\
用于对程序外的字符进行编码的类型。

*`StateType`*\
一种类型，此类型可用于表示字符表示形式的内部和外部类型之间转换的中间状态。

## <a name="remarks"></a>备注

类模板描述可用作 [区域设置 facet](../standard-library/locale-class.md#facet_class)的对象，用于控制类型的值序列 *`CharType`* 和类型的值序列之间的转换 *`Byte`* 。 类描述 *`StateType`* 转换，类的对象 *`StateType`* 存储转换期间的任何必要状态信息。

内部编码使用每个字符的固定字节数的表示形式，通常为类型 **`char`** 或类型 **`wchar_t`** 。

对于任何区域设置 facet，静态对象 `id` 的初始存储值为零。 首次尝试访问其存储值后，将在 `id` 中存储唯一正值。

和的模板版本 [`do_in`](#do_in) [`do_out`](#do_out) 始终返回 `codecvt_base::noconv` 。

C++ 标准库定义了若干显式专用化：

```cpp
template<>
codecvt<wchar_t, char, mbstate_t>
```

在 **`wchar_t`** 和序列之间转换 **`char`** 。

```cpp
template<>
codecvt<char16_t, char, mbstate_t>
```

在 **`char16_t`** 以 utf-16 编码的序列和 **`char`** 按 utf-8 编码的序列之间转换。

```cpp
template<>
codecvt<char32_t, char, mbstate_t>
```

在 **`char32_t`** 编码为 32 (UCS-4) 和 **`char`** 序列编码为 utf-8 的序列之间转换。

### <a name="constructors"></a>构造函数

|构造函数|说明|
|-|-|
|[`codecvt`](#codecvt)|用作区域设置 facet 以处理转换的 `codecvt` 类的对象的构造函数。|

### <a name="typedefs"></a>Typedef

|类型名称|描述|
|-|-|
|[`extern_type`](#extern_type)|用于外部表示形式的字符类型。|
|[`intern_type`](#intern_type)|用于内部表示形式的字符类型。|
|[`state_type`](#state_type)|一种字符类型，此类型用于表示内部和外部表示形式进行转换期间的中间状态。|

### <a name="member-functions"></a>成员函数

|成员函数|说明|
|-|-|
|[`always_noconv`](#always_noconv)|测试是否不需要完成转换。|
|[`do_always_noconv`](#do_always_noconv)|为测试是否不需要完成转换而调用的虚拟函数。|
|[`do_encoding`](#do_encoding)|一种虚拟函数，用于测试流的编码是否 `Byte` 依赖于状态、 `Byte` 使用的值与生成的值之间的比率 `CharType` 是否恒定，如果是，则确定此比率的值。|
|[`do_in`](#do_in)|一种虚拟函数，通过调用此函数可将内部值序列转换 `Byte` 为外部 `CharType` 值序列。|
|[`do_length`](#do_length)|一种虚拟函数，该函数确定 `Byte` 给定外部值序列中的多少个值 `Byte` 不超过给定的内部值数 `CharType` 并返回该值的数目 `Byte` 。|
|[`do_max_length`](#do_max_length)|返回生成一个内部 `CharType` 所需的最大外部字节数的虚拟函数。|
|[`do_out`](#do_out)|一种虚拟函数，通过调用此函数可将内部值序列转换 `CharType` 为外部字节序列。|
|[`do_unshift`](#do_unshift)|一种虚拟函数，通过调用此函数可提供 `Byte` 依赖于状态的转换中所需的值以完成值序列中的最后一个字符 `Byte` 。|
|[`encoding`](#encoding)|测试流的编码是否 `Byte` 依赖于状态、 `Byte` 使用的值与生成的值之间的比率是否 `CharType` 恒定，如果是，则确定此比率的值。|
|[`in`](#in)|将值序列的外部表示形式转换 `Byte` 为值序列的内部表示形式 `CharType` 。|
|[`length`](#length)|确定 `Byte` 给定外部值序列中的多少个值 `Byte` 不超过给定的内部 `CharType` 值数并返回该值的数目 `Byte` 。|
|[`max_length`](#max_length)|返回 `Byte` 生成一个内部所需的最大外部值数 `CharType` 。|
|[`out`](#out)|将内部值序列转换 `CharType` 为外部值的序列 `Byte` 。|
|[`unshift`](#unshift)|提供 `Byte` 在依赖于状态的转换中完成值序列中最后一个字符所需的外部值 `Byte` 。|

## <a name="requirements"></a>要求

**标头：**`<locale>`

**命名空间：** `std`

## <a name="codecvtalways_noconv"></a><a name="always_noconv"></a> `codecvt::always_noconv`

测试是否无需进行转换。

```cpp
bool always_noconv() const throw();
```

### <a name="return-value"></a>返回值

一个布尔值， **`true`** 如果无需进行转换，则为; **`false`** 如果至少有一个需要完成，则为。

### <a name="remarks"></a>备注

此成员函数返回 [`do_always_noconv`](#do_always_noconv) 。

### <a name="example"></a>示例

```cpp
// codecvt_always_noconv.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = use_facet<codecvt<char, char, mbstate_t>>
      ( loc ).always_noconv( );

   if ( result1 )
      cout << "No conversion is needed." << '\n';
   else
      cout << "At least one conversion is required." << '\n';

   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t>>
      ( loc ).always_noconv( );

   if ( result2 )
      cout << "No conversion is needed." << '\n';
   else
      cout << "At least one conversion is required." << '\n';
}
```

```Output
No conversion is needed.
At least one conversion is required.
```

## <a name="codecvtcodecvt"></a><a name="codecvt"></a> `codecvt::codecvt`

用作区域设置 facet 以处理转换的 codecvt 类的对象的构造函数。

```cpp
explicit codecvt(size_t refs = 0);
```

### <a name="parameters"></a>参数

*`refs`*\
用于指定对象的内存管理类型的整数值。

### <a name="remarks"></a>备注

参数的可能值 *`refs`* 及其重要性为：

- 0：对象的生存期由包含该对象的区域设置管理。

- 1：必须手动管理对象的生存期。


- 2：未定义这些值。

构造函数用初始化其 `locale::facet` 基对象 [`locale::facet`](../standard-library/locale-class.md#facet_class) `(refs)` 。

## <a name="codecvtdo_always_noconv"></a><a name="do_always_noconv"></a> `codecvt::do_always_noconv`

一种虚拟函数，通过调用此函数可测试是否无需进行转换。

```cpp
virtual bool do_always_noconv() const throw();
```

### <a name="return-value"></a>返回值

**`true`** 仅在每次调用或返回时，受保护的虚拟成员函数才返回 [`do_in`](#do_in) [`do_out`](#do_out) `noconv` 。

模板版本始终返回 **`true`** 。

### <a name="example"></a>示例

请参阅的示例 [`always_noconv`](#always_noconv) ，它调用 `do_always_noconv` 。

## <a name="codecvtdo_encoding"></a><a name="do_encoding"></a> `codecvt::do_encoding`

一种虚拟函数，用于测试流的编码是否 `Byte` 依赖于状态、 `Byte` 使用的值与生成的值之间的比率 `CharType` 是否恒定，如果是，则确定此比率的值。

```cpp
virtual int do_encoding() const throw();
```

### <a name="return-value"></a>返回值

受保护的虚拟成员函数返回：

- 如果类型序列的编码依赖于状态，则为-1 `extern_type` 。

- 如果编码涉及不同长度的序列，则为 0。

- *`N`* 如果编码仅涉及长度的序列，则为 *`N`*

### <a name="example"></a>示例

请参阅 [encoding](#encoding) 的示例，它调用 `do_encoding`。

## <a name="codecvtdo_in"></a><a name="do_in"></a> codecvt：:d o_in

一种虚拟函数，通过调用此函数可将外部值序列转换 `Byte` 为内部 `CharType` 值序列。

```cpp
virtual result do_in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>参数

*`state`*\
每次调用成员函数时保留的转换状态。

*`first1`*\
指向待转换序列开头的指针。

*`last1`*\
指向待转换序列末尾的指针。

*`next1`*\
指向超出已转换序列末尾到第一个未转换字符的指针。

*`first2`*\
指向已转换序列开头的指针。

*`last2`*\
指向已转换序列末尾的指针。

*`next2`*\
指向 `CharType` 上次转换后的，指向 `CharType` 目标序列中第一个未更改字符的指针。

### <a name="return-value"></a>返回值

返回指示操作成功、部分成功或失败的值。 该函数返回：

- `codecvt_base::error` 如果源序列的格式不正确，则为。

- 如果函数不执行任何转换，则为 `codecvt_base::noconv`。

- `codecvt_base::ok` 如果转换成功，则为。

- `codecvt_base::partial` 如果源不足或目标不够大，则转换成功。

### <a name="remarks"></a>备注

*`state`* 必须表示新源序列开头的初始转换状态。 此函数根据需要来更改其存储的值以反映成功转换的当前状态。 否则未指定其存储的值。

### <a name="example"></a>示例

请参阅的示例 [`in`](#in) ，它调用 `do_in` 。

## <a name="codecvtdo_length"></a><a name="do_length"></a> `codecvt::do_length`

一种虚拟函数，该函数确定 `Byte` 给定外部值序列中的多少个值 `Byte` 不超过给定的内部值数 `CharType` 并返回该值的数目 `Byte` 。

```cpp
virtual int do_length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>参数

*`state`*\
每次调用成员函数时保留的转换状态。

*`first1`*\
指向外部序列开头的指针。

*`last1`*\
指向外部序列末尾的指针。

*`len2`*\
`Byte`成员函数可返回的最大值数。

### <a name="return-value"></a>返回值

一个整数，表示位于 [，) 的外部源序列定义的最大 *len2* 转换数的计数，而不是大于 len2 `first1` `last1` 。

### <a name="remarks"></a>备注

受保护的虚拟成员函数将有效地调用状态 `do_in( state, first1, last1, next1, buf, buf + len2, next2)` () 、某些缓冲区 *state* `buf` 和指针和的副本 `next1` `next2` 。

然后返回 `next2`  -  `buf` 。 它计算在 [，) 的源序列定义的 *len2* 转换的最大数目，不能超过 `first1` len2 `last1` 。

模板版本始终返回 *`last1`*  -  *`first1`* 和中较小的一个 *`len2`* 。

### <a name="example"></a>示例

请参阅的示例 [`length`](#length) ，它调用 `do_length` 。

## <a name="codecvtdo_max_length"></a><a name="do_max_length"></a> `codecvt::do_max_length`

返回 `Byte` 生成一个内部所需的最大外部值数的虚函数 `CharType` 。

```cpp
virtual int do_max_length() const throw();
```

### <a name="return-value"></a>返回值

`Byte`生成一个所需的最大值数 `CharType` 。

### <a name="remarks"></a>备注

受保护的虚拟成员函数将返回可供 [`do_length`](#do_length) `( first1, last1, 1)` 和的任意有效值返回的最大允许值 *`first1`* *`last1`* 。

### <a name="example"></a>示例

请参阅的示例 [`max_length`](#max_length) ，它调用 `do_max_length` 。

## <a name="codecvtdo_out"></a><a name="do_out"></a> `codecvt::do_out`

一种虚拟函数，通过调用此函数可将内部值序列转换 `CharType` 为外部 `Byte` 值序列。

```cpp
virtual result do_out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>参数

*`state`*\
每次调用成员函数时保留的转换状态。

*`first1`*\
指向待转换序列开头的指针。

*`last1`*\
指向待转换序列末尾的指针。

*`next1`*\
指向 `CharType` 上次转换后转换后的第一个未转换的指针的引用 `CharType` 。

*`first2`*\
指向已转换序列开头的指针。

*`last2`*\
指向已转换序列末尾的指针。

*`next2`*\
指向 `Byte` 上次转换后转换后的第一个未转换的指针的引用 `Byte` 。

### <a name="return-value"></a>返回值

该函数返回：

- `codecvt_base::error` 如果源序列的格式不正确，则为。

- 如果函数不执行任何转换，则为 `codecvt_base::noconv`。

- `codecvt_base::ok` 如果转换成功，则为。

- `codecvt_base::partial` 如果源不足，或者目标不够大，则无法成功转换。

### <a name="remarks"></a>备注

*`state`* 必须表示新源序列开头的初始转换状态。 此函数根据需要来更改其存储的值以反映成功转换的当前状态。 否则未指定其存储的值。

### <a name="example"></a>示例

请参阅 [out](#out) 的示例，它调用 `do_out`。

## <a name="codecvtdo_unshift"></a><a name="do_unshift"></a> `codecvt::do_unshift`

一种虚拟函数，通过调用此函数可提供 `Byte` 依赖于状态的转换中所需的值以完成值序列中的最后一个字符 `Byte` 。

```cpp
virtual result do_unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>参数

*`state`*\
每次调用成员函数时保留的转换状态。

*`first2`*\
指向目标范围内第一个位置的指针。

*`last2`*\
指向目标范围内最后一个位置的指针。

*`next2`*\
指向目标序列中第一个未更改元素的指针。

### <a name="return-value"></a>返回值

该函数返回：

- `codecvt_base::error` 如果 *状态* 表示无效状态

- 如果该函数不执行任何转换，则为 `codecvt_base::noconv`

- `codecvt_base::ok` 如果转换成功

- `codecvt_base::partial` 如果目标不够大，转换成功

### <a name="remarks"></a>备注

受保护的虚拟成员函数尝试将源元素 `CharType` (0) 转换为它在 [，) 内存储的目标序列 `first2` `last2` （终止元素 `Byte` (0) 除外）。 它始终存储在指向 *`next2`* 目标序列中第一个未更改元素的指针中。

*`State`* 必须表示新源序列开头的初始转换状态。 此函数根据需要来更改其存储的值以反映成功转换的当前状态。 通常情况下，将源元素转换 `CharType` (0) 会使当前状态处于初始转换状态。

### <a name="example"></a>示例

请参阅的示例 [`unshift`](#unshift) ，它调用 `do_unshift` 。

## <a name="codecvtencoding"></a><a name="encoding"></a> `codecvt::encoding`

测试流的编码是否 `Byte` 依赖于状态、 `Byte` 使用的值与生成的值之间的比率是否 `CharType` 恒定，如果是，则确定此比率的值。

```cpp
int encoding() const throw();
```

### <a name="return-value"></a>返回值

如果返回值为正，则该值是 `Byte` 生成字符所需的常量字符数 `CharType` 。

受保护的虚拟成员函数返回：

- 如果类型序列的编码依赖于状态，则为-1 `extern_type` 。

- 如果编码涉及不同长度的序列，则为 0。

- *`N`* 如果编码仅涉及长度的序列，则为 *`N`* 。

### <a name="remarks"></a>备注

此成员函数返回 [do_encoding](#do_encoding)。

### <a name="example"></a>示例

```cpp
// codecvt_encoding.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   int result1 = use_facet<codecvt<char, char, mbstate_t>> ( loc ).encoding ( );
   cout << result1 << '\n';
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t>> ( loc ).encoding( );
   cout << result1 << '\n';
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t>> ( loc ).encoding( );
   cout << result1 << '\n';
}
```

```Output
1
1
1
```

## <a name="codecvtextern_type"></a><a name="extern_type"></a> `codecvt::extern_type`

用于外部表示形式的字符类型。

```cpp
typedef Byte extern_type;
```

### <a name="remarks"></a>备注

类型是模板参数 `Byte` 的同义词。

## <a name="codecvtin"></a><a name="in"></a> codecvt：： in

将值序列的外部表示形式转换 `Byte` 为值序列的内部表示形式 `CharType` 。

```cpp
result in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>参数

*`state`*\
每次调用成员函数时保留的转换状态。

*`first1`*\
指向待转换序列开头的指针。

*`last1`*\
指向待转换序列末尾的指针。

*`next1`*\
指向超出已转换序列末尾到第一个未转换字符的指针。

*`first2`*\
指向已转换序列开头的指针。

*`last2`*\
指向已转换序列末尾的指针。

*`next2`*\
指向 `CharType` 上次转换 `Chartype` 为目标序列中第一个未更改字符之后的。

### <a name="return-value"></a>返回值

返回指示操作成功、部分成功或失败的值。 该函数返回：

- `codecvt_base::error` 如果源序列的格式不正确，则为。

- 如果函数不执行任何转换，则为 `codecvt_base::noconv`。

- `codecvt_base::ok` 如果转换成功，则为。

- `codecvt_base::partial` 如果源不足，或者目标不够大，则无法成功转换。

### <a name="remarks"></a>备注

*`state`* 必须表示新源序列开头的初始转换状态。 此函数根据需要来更改其存储的值以反映成功转换的当前状态。 在部分转换后， *`state`* 必须将设置为，以允许在新字符到达时恢复转换。

此成员函数返回 [`do_in`](#do_in) `( state, first1,  last1,  next1, first2, last2,  next2)` 。

### <a name="example"></a>示例

```cpp
// codecvt_in.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   const char* pszExt = "This is the string to be converted!";
   wchar_t pwszInt [LEN+1];
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));
   const char* pszNext;
   wchar_t* pwszNext;
   mbstate_t state = {0}; // zero-initialization represents the initial conversion state for mbstate_t
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t>>
     ( loc ).in( state,
          pszExt, &pszExt[strlen(pszExt)], pszNext,
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );
   pwszInt[strlen(pszExt)] = 0;
   wcout << ( res!=codecvt_base::error ?  L"It worked! " : L"It didn't work! " )
       << L"The converted string is:\n ["
       << &pwszInt[0]
       << L"]" << '\n';
   exit(-1);
}
```

```Output
It worked! The converted string is:
[This is the string to be converted!]
```

## <a name="codecvtintern_type"></a><a name="intern_type"></a> `codecvt::intern_type`

用于内部表示形式的字符类型。

```cpp
typedef CharType intern_type;
```

### <a name="remarks"></a>备注

类型是模板参数 `CharType` 的同义词。

## <a name="codecvtlength"></a><a name="length"></a> codecvt：： length

确定 `Byte` 给定外部值序列中的多少个值 `Byte` 不超过给定的内部 `CharType` 值数并返回该值的数目 `Byte` 。

```cpp
int length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>参数

*`state`*\
每次调用成员函数时保留的转换状态。

*`first1`*\
指向外部序列开头的指针。

*`last1`*\
指向外部序列末尾的指针。

*`len2`*\
可由成员函数返回的最大字节数。

### <a name="return-value"></a>返回值

一个整数，表示 *`len2`* 在 [，) 的外部源序列定义的最大转换数的计数，而不是大于 `first1` `last1` 。

### <a name="remarks"></a>备注

此成员函数返回 [`do_length`](#do_length) `( state, first1, last1, len2)` 。

### <a name="example"></a>示例

```cpp
// codecvt_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   const char* pszExt = "This is the string whose length is to be measured!";
   mbstate_t state = {0}; // zero-initialization represents the initial conversion state for mbstate_t
   locale loc("C"); // English_Britain"); //German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t>>
     ( loc ).length( state,
          pszExt, &pszExt[strlen(pszExt)], LEN );
   cout << "The length of the string is: ";
   wcout << res;
   cout << "." << '\n';
   exit(-1);
}
```

```Output
The length of the string is: 50.
```

## <a name="codecvtmax_length"></a><a name="max_length"></a> `codecvt::max_length`

返回 `Byte` 生成一个内部所需的最大外部值数 `CharType` 。

```cpp
int max_length() const throw();
```

### <a name="return-value"></a>返回值

`Byte`生成一个所需的最大值数 `CharType` 。

### <a name="remarks"></a>备注

此成员函数返回 [`do_max_length`](#do_max_length) 。

### <a name="example"></a>示例

```cpp
// codecvt_max_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc( "C");//English_Britain" );//German_Germany
   int res = use_facet<codecvt<char, char, mbstate_t>>
     ( loc ).max_length( );
   wcout << res << '\n';
}
```

```Output
1
```

## <a name="codecvtout"></a><a name="out"></a> `codecvt::out`

将内部值序列转换 `CharType` 为外部值的序列 `Byte` 。

```cpp
result out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>参数

*`state`*\
每次调用成员函数时保留的转换状态。

*`first1`*\
指向待转换序列开头的指针。

*`last1`*\
指向待转换序列末尾的指针。

*`next1`*\
引用指向上次转换后的第一个未转换的指针 `CharType` `CharType` 。

*`first2`*\
指向已转换序列开头的指针。

*`last2`*\
指向已转换序列末尾的指针。

*`next2`*\
引用指向上次转换后的第一个未转换的指针 `Byte` `Byte` 。

### <a name="return-value"></a>返回值

此成员函数返回 [`do_out`](#do_out) `( state, first1, last1, next1, first2, last2, next2)` 。

### <a name="remarks"></a>备注

有关详细信息，请参阅 [`codecvt::do_out`](#do_out)。

### <a name="example"></a>示例

```cpp
// codecvt_out.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
#include <wchar.h>
using namespace std;
#define LEN 90
int main( )
{
    char pszExt[LEN + 1];
    const wchar_t* pwszInt = L"This is the wchar_t string to be converted.";
    memset(&pszExt[0], 0, (sizeof(char)) * (LEN + 1));
    char* pszNext;
    const wchar_t* pwszNext;
    mbstate_t state;
    locale loc("C");//English_Britain");//German_Germany
    int res = use_facet<codecvt<wchar_t, char, mbstate_t>>
        (loc).out(state,
            pwszInt, &pwszInt[wcslen(pwszInt)], pwszNext,
            pszExt, &pszExt[wcslen(pwszInt)], pszNext);
    pszExt[wcslen(pwszInt)] = 0;
    cout << (res != codecvt_base::error ? "It worked: " : "It didn't work: ")
        << "The converted string is:\n ["
        << &pszExt[0]
        << "]" << '\n';

}
```

```Output
It worked: The converted string is:
[This is the wchar_t string to be converted.]
```

## <a name="codecvtstate_type"></a><a name="state_type"></a> `codecvt::state_type`

一种字符类型，此类型用于表示内部和外部表示形式进行转换期间的中间状态。

```cpp
typedef StateType state_type;
```

### <a name="remarks"></a>备注

类型是模板参数 `StateType` 的同义词。

## <a name="codecvtunshift"></a><a name="unshift"></a> codecvt：： unshift

提供 `Byte` 依赖于状态的转换中所需的值以完成值序列中的最后一个字符 `Byte` 。

```cpp
result unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>参数

*`state`*\
每次调用成员函数时保留的转换状态。

*`first2`*\
指向目标范围内第一个位置的指针。

*`last2`*\
指向目标范围内最后一个位置的指针。

*`next2`*\
指向目标序列中第一个未更改元素的指针。

### <a name="return-value"></a>返回值

该函数返回：

- `codecvt_base::error` 如果 state 表示无效状态，则为。

- 如果函数不执行任何转换，则为 `codecvt_base::noconv`。

- `codecvt_base::ok` 如果转换成功，则为。

- `codecvt_base::partial` 如果目标不够大，则无法成功转换。

### <a name="remarks"></a>备注

受保护的虚拟成员函数尝试将源元素 `CharType` (0) 转换为它在 [，) 内存储的目标序列 `first2` `last2` （终止元素 `Byte` (0) 除外）。 它始终存储在指向 *`next2`* 目标序列中第一个未更改元素的指针中。

*`state`* 必须表示新源序列开头的初始转换状态。 此函数根据需要来更改其存储的值以反映成功转换的当前状态。 通常情况下，将源元素转换 `CharType` (0) 会使当前状态处于初始转换状态。

此成员函数返回 [`do_unshift`](#do_unshift) `( state, first2, last2, next2 )` 。

## <a name="see-also"></a>另请参阅

[`<locale>`](../standard-library/locale.md)\
[代码页](../c-runtime-library/code-pages.md)\
[区域设置名称、语言和国家/地区字符串](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
