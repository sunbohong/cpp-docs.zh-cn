---
description: 了解更多： &lt; 字符串 &gt; 函数
title: '&lt;string&gt; 函数'
ms.date: 11/04/2016
f1_keywords:
- string/std::getline
- string/std::stod
- string/std::stof
- string/std::stoi
- string/std::stol
- string/std::stold
- string/std::stoll
- string/std::stoul
- string/std::stoull
- string/std::swap
- string/std::to_string
- string/std::to_wstring
ms.assetid: 1a4ffd11-dce5-4cc6-a043-b95de034c7c4
helpviewer_keywords:
- std::getline [C++]
- std::stod [C++]
- std::stof [C++]
- std::stoi [C++]
- std::stol [C++]
- std::stold [C++]
- std::stoll [C++]
- std::stoul [C++]
- std::stoull [C++]
- std::swap [C++]
- std::to_string [C++]
- std::to_wstring [C++]
ms.openlocfilehash: 859cb6db2e02ad5e915b5d8f3ed31aaf7e443580
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183732"
---
# <a name="ltstringgt-functions"></a>&lt;string&gt; 函数

[getline](#getline)\
[stod](#stod)\
[stof](#stof)\
[stoi](#stoi)\
[stol](#stol)\
[stold](#stold)\
[stoll](#stoll)\
[stoul](#stoul)\
[stoull](#stoull)\
[购](#swap)\
[to_string](#to_string)\
[to_wstring](#to_wstring)

## <a name="getline"></a><a name="getline"></a> getline

将字符串从输入流中一行一行地提取出来。

```cpp
// (1) delimiter as parameter
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& in_stream,
    basic_string<CharType, Traits, Allocator>& str,
    CharType delimiter);

template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>&& in_stream,
    basic_string<CharType, Traits, Allocator>& str,
    const CharType delimiter);

// (2) default delimiter used
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& in_stream,
    basic_string<CharType, Traits, Allocator>& str);

template <class Allocator, class Traits, class Allocator>
basic_istream<Allocator, Traits>& getline(
    basic_istream<Allocator, Traits>&& in_stream,
    basic_string<Allocator, Traits, Allocator>& str);
```

### <a name="parameters"></a>parameters

*in_stream*\
要从其中提取字符串的输入流。

*字符串*\
从输入流读取的字符将放入的字符串。

*后面*\
行分隔符。

### <a name="return-value"></a>返回值

输入流 *in_stream*。

### <a name="remarks"></a>备注

标记为 `(1)` 从 *in_stream* 提取字符直到找到 *分隔符* 的函数签名对，并将它们存储在 *字符串* 中。

标记为 `(2)` 使用换行符作为默认行分隔符，并表现为的函数签名对 `getline(in_stream, str, in_stream. widen('\n'))` 。

每对函数中的第二个函数是第一个的模拟，它的作用是支持 [rvalue 引用](../cpp/lvalues-and-rvalues-visual-cpp.md)。

发生下列情况之一时，提取将停止：

- 在文件末尾， *in_stream* 的内部状态标志设置为 `ios_base::eofbit` 。

- 函数提取了比较等于 *分隔符* 的元素后。 元素不会返回或追加到受控序列。

- 函数提取 `str.` [max_size](../standard-library/basic-string-class.md#max_size)元素后。 *In_stream* 的内部状态标志设置为 `ios_base::failbit` 。

- 除前面列出的其他错误外， *in_stream* 的内部状态标志设置为 `ios_base::badbit` 。

有关内部状态标志的信息，请参阅 [ios_base::iostate](../standard-library/ios-base-class.md#iostate)。

如果该函数未提取任何元素，则 *in_stream* 的内部状态标志设置为 `ios_base::failbit` 。 在任何情况下，都将 `getline` 返回 *in_stream*。

如果引发异常，则 *in_stream* 和 *str* 处于有效状态。

### <a name="example"></a>示例

以下代码演示两种模式下的 `getline()`：第一种使用默认分隔符（换行），第二种使用空格作为分隔符。 文件尾字符（键盘上的 CTRL-Z）用于控制 while 循环的终止。 此值将的内部状态标志设置 `cin` 为 `eofbit` ，在第二个 while 循环工作正常时，必须使用 [basic_ios：： Clear ( # B1 ](../standard-library/basic-ios-class.md#clear) 来清除该标志。

```cpp
// compile with: /EHsc /W4
#include <string>
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    string str;
    vector<string> v1;
    cout << "Enter a sentence, press ENTER between sentences. (Ctrl-Z to stop): " << endl;
    // Loop until end-of-file (Ctrl-Z) is input, store each sentence in a vector.
    // Default delimiter is the newline character.
    while (getline(cin, str)) {
        v1.push_back(str);
    }

    cout << "The following input was stored with newline delimiter:" << endl;
    for (const auto& p : v1) {
        cout << p << endl;
    }

    cin.clear();

    vector<string> v2;
    // Now try it with a whitespace delimiter
    while (getline(cin, str, ' ')) {
        v2.push_back(str);
    }

    cout << "The following input was stored with whitespace as delimiter:" << endl;
    for (const auto& p : v2) {
        cout << p << endl;
    }
}
```

## <a name="stod"></a><a name="stod"></a> stod

将字符序列转换为 **`double`** 。

```cpp
double stod(
    const string& str,
    size_t* idx = 0);

double stod(
    const wstring& str,
    size_t* idx = 0
;
```

### <a name="parameters"></a>parameters

*字符串*\
要转换的字符序列。

*idx*\
首个未转换字符的索引值。

### <a name="return-value"></a>返回值

**`double`** 值。

### <a name="remarks"></a>备注

函数将 *str* 中的元素序列转换为类型的值 **`double`** ，就像调用一样 `strtod( str.c_str(), _Eptr)` ，其中， `_Eptr` 是函数的内部对象。 如果为 `str.c_str() == *_Eptr` ，则它将引发类型的对象 `invalid_argument` 。 如果此类调用将设置 `errno`，它将引发 `out_of_range` 类型的对象。 否则，如果 *idx* 不是 null 指针，该函数将存储 `*_Eptr -  str.c_str()` 在中 `*idx` 并返回值。

## <a name="stof"></a><a name="stof"></a> stof

将字符序列转换为浮动的。

```cpp
float stof(
    const string& str,
    size_t* idx = 0);

float stof(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>parameters

*字符串*\
要转换的字符序列。

*idx*\
首个未转换字符的索引值。

### <a name="return-value"></a>返回值

**`float`** 值。

### <a name="remarks"></a>备注

函数将 *str* 中的元素序列转换为类型的值 **`float`** ，就像调用一样 `strtof( str.c_str(), _Eptr)` ，其中， `_Eptr` 是函数的内部对象。 如果为 `str.c_str() == *_Eptr` ，则它将引发类型的对象 `invalid_argument` 。 如果此类调用将设置 `errno`，它将引发 `out_of_range` 类型的对象。 否则，如果 *idx* 不是 null 指针，该函数将存储 `*_Eptr -  str.c_str()` 在中 `*idx` 并返回值。

## <a name="stoi"></a><a name="stoi"></a> stoi

将字符序列转换为整数。

```cpp
int stoi(
    const string& str,
    size_t* idx = 0,
    int base = 10);

int stoi(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="return-value"></a>返回值

整数值。

### <a name="parameters"></a>parameters

*字符串*\
要转换的字符序列。

*idx*\
首个未转换字符的索引值。

*基座*\
要使用的号码基。

### <a name="remarks"></a>备注

函数 `stoi` 将 *str* 中字符的序列转换为类型的值 **`int`** 并返回值。 例如，在传递字符序列“10”时，`stoi` 返回的值为整数 10.

`stoi``strtol`在以方式调用时，其行为与单字节字符的函数相似 `strtol( str.c_str(), _Eptr, idx)` ，其中， `_Eptr` 是函数的内部对象; `wcstol` 对于宽字符，则其行为方式类似 `wcstol(Str.c_str(), _Eptr, idx)` 。 有关详细信息，请参阅 [strtol、wcstol、_strtol_l、_wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)。

如果为 `str.c_str() == *_Eptr` ，则 `stoi` 引发类型的对象 `invalid_argument` 。 如果此类调用将设置 `errno` ，或者如果返回值无法表示为类型的对象 **`int`** ，则它将引发类型的对象 `out_of_range` 。 否则，如果 *idx* 不是 null 指针，该函数将存储 `*_Eptr - str.c_str()` 在中 `*idx` 。

## <a name="stol"></a><a name="stol"></a> stol

将字符序列转换为 **`long`** 。

```cpp
long stol(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long stol(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>parameters

*字符串*\
要转换的字符序列。

*idx*\
首个未转换字符的索引值。

*基座*\
要使用的号码基。

### <a name="return-value"></a>返回值

长整数的值。

### <a name="remarks"></a>备注

函数将 *str* 中的元素序列转换为类型的值 **`long`** ，就像调用一样 `strtol( str.c_str(), _Eptr, idx)` ，其中， `_Eptr` 是函数的内部对象。 如果为 `str.c_str() == *_Eptr` ，则它将引发类型的对象 `invalid_argument` 。 如果此类调用将设置 `errno`，它将引发 `out_of_range` 类型的对象。 否则，如果 *idx* 不是 null 指针，该函数将存储 `*_Eptr -  str.c_str()` 在中 `*idx` 并返回值。

## <a name="stold"></a><a name="stold"></a> stold

将字符序列转换为 **`long double`** 。

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>parameters

*字符串*\
要转换的字符序列。

*idx*\
首个未转换字符的索引值。

### <a name="return-value"></a>返回值

**`long double`** 值。

### <a name="remarks"></a>备注

函数将 *str* 中的元素序列转换为类型的值 **`long double`** ，就像调用一样 `strtold( str.c_str(), _Eptr)` ，其中， `_Eptr` 是函数的内部对象。 如果为 `str.c_str() == *_Eptr` ，则它将引发类型的对象 `invalid_argument` 。 如果此类调用将设置 `errno`，它将引发 `out_of_range` 类型的对象。 否则，如果 *idx* 不是 null 指针，该函数将存储 `*_Eptr -  str.c_str()` 在中 `*idx` 并返回值。

## <a name="stoll"></a><a name="stoll"></a> stoll

将字符序列转换为 **`long long`** 。

```cpp
long long stoll(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long long stoll(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>parameters

*字符串*\
要转换的字符序列。

*idx*\
首个未转换字符的索引值。

*基座*\
要使用的号码基。

### <a name="return-value"></a>返回值

**`long long`** 值。

### <a name="remarks"></a>备注

函数将 *str* 中的元素序列转换为类型的值 **`long long`** ，就像调用一样 `strtoll( str.c_str(), _Eptr, idx)` ，其中， `_Eptr` 是函数的内部对象。 如果为 `str.c_str() == *_Eptr` ，则它将引发类型的对象 `invalid_argument` 。 如果此类调用将设置 `errno`，它将引发 `out_of_range` 类型的对象。 否则，如果 *idx* 不是 null 指针，该函数将存储 `*_Eptr -  str.c_str()` 在中 `*idx` 并返回值。

## <a name="stoul"></a><a name="stoul"></a> stoul

将字符序列转换为无符号长整数。

```cpp
unsigned long stoul(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long stoul(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>parameters

*字符串*\
要转换的字符序列。

*idx*\
首个未转换字符的索引值。

*基座*\
要使用的号码基。

### <a name="return-value"></a>返回值

无符号长整数的值。

### <a name="remarks"></a>备注

函数将 *str* 中的元素序列转换为类型的值 **`unsigned long`** ，就像调用一样 `strtoul( str.c_str(), _Eptr, idx)` ，其中， `_Eptr` 是函数的内部对象。 如果为 `str.c_str() == *_Eptr` ，则它将引发类型的对象 `invalid_argument` 。 如果此类调用将设置 `errno`，它将引发 `out_of_range` 类型的对象。 否则，如果 *idx* 不是 null 指针，该函数将存储 `*_Eptr -  str.c_str()` 在中 `*idx` 并返回值。

## <a name="stoull"></a><a name="stoull"></a> stoull

将字符序列转换为 **`unsigned long long`** 。

```cpp
unsigned long long stoull(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long long stoull(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>parameters

*字符串*\
要转换的字符序列。

*idx*\
首个未转换字符的索引值。

*基座*\
要使用的号码基。

### <a name="return-value"></a>返回值

**`unsigned long long`** 值。

### <a name="remarks"></a>备注

函数将 *str* 中的元素序列转换为类型的值 **`unsigned long long`** ，就像调用一样 `strtoull( str.c_str(), _Eptr, idx)` ，其中， `_Eptr` 是函数的内部对象。 如果为 `str.c_str() == *_Eptr` ，则它将引发类型的对象 `invalid_argument` 。 如果此类调用将设置 `errno`，它将引发 `out_of_range` 类型的对象。 否则，如果 *idx* 不是 null 指针，该函数将存储 `*_Eptr -  str.c_str()` 在中 `*idx` 并返回值。

## <a name="swap"></a><a name="swap"></a> 购

交换两个字符串的字符数组。

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>parameters

*左中*\
一个字符串，其元素将与另一个字符串的元素交换。

*然后*\
要与第一个字符串交换元素的另一个字符串。

### <a name="remarks"></a>备注

此模板函数会执行 *左侧* 专用成员函数。[交换](../standard-library/basic-string-class.md#swap) 字符串的 (*右*) ，可保证恒定的复杂性。

### <a name="example"></a>示例

```cpp
// string_swap.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an object of type basic_string<char>
   string s1 ( "Tweedledee" );
   string s2 ( "Tweedledum" );
   cout << "Before swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   swap ( s1 , s2 );
   cout << "\nAfter swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;
}
```

```Output
Before swapping string s1 and s2:
The basic_string s1 = Tweedledee.
The basic_string s2 = Tweedledum.

After swapping string s1 and s2:
The basic_string s1 = Tweedledum.
The basic_string s2 = Tweedledee.
```

## <a name="to_string"></a><a name="to_string"></a> to_string

将一个值转换为 `string`。

```cpp
string to_string(int value);
string to_string(unsigned int value);
string to_string(long value);
string to_string(unsigned long value);
string to_string(long long value);
string to_string(unsigned long long value);
string to_string(float value);
string to_string(double value);
string to_string(long double value);
```

### <a name="parameters"></a>parameters

*负值*\
要转换的值。

### <a name="return-value"></a>返回值

表示该值的 `string`。

### <a name="remarks"></a>备注

函数将 *值* 转换为存储在函数内部数组对象中的元素序列 `Buf` ，就像调用一样 `sprintf(Buf, Fmt, value)` ，其中 `Fmt` 是

- `"%d"` 如果 *值* 的类型为 **`int`**

- `"%u"` 如果 *值* 的类型为 **`unsigned int`**

- `"%ld"` 如果 *值* 的类型为 **`long`**

- `"%lu"` 如果 *值* 的类型为 **`unsigned long`**

- `"%lld"` 如果 *值* 的类型为 **`long long`**

- `"%llu"` 如果 *值* 的类型为 **`unsigned long long`**

- `"%f"` 如果 *值* 的类型为 **`float`** 或 **`double`**

- `"%Lf"` 如果 *值* 的类型为 **`long double`**

该函数返回 `string(Buf)`。

## <a name="to_wstring"></a><a name="to_wstring"></a> to_wstring

将一个值转换为宽字符串。

```cpp
wstring to_wstring(int value);
wstring to_wstring(unsigned int value);
wstring to_wstring(long value);
wstring to_wstring(unsigned long value);
wstring to_wstring(long long value);
wstring to_wstring(unsigned long long value);
wstring to_wstring(float value);
wstring to_wstring(double value);
wstring to_wstring(long double value);
```

### <a name="parameters"></a>parameters

*负值*\
要转换的值。

### <a name="return-value"></a>返回值

表示该值的宽字符串。

### <a name="remarks"></a>备注

函数将 *值* 转换为存储在函数内部数组对象中的元素序列 `Buf` ，就像调用一样 `swprintf(Buf, Len, Fmt, value)` ，其中 `Fmt` 是

- `L"%d"` 如果 *值* 的类型为 **`int`**

- `L"%u"` 如果 *值* 的类型为 **`unsigned int`**

- `L"%ld"` 如果 *值* 的类型为 **`long`**

- `L"%lu"` 如果 *值* 的类型为 **`unsigned long`**

- `L"%lld"` 如果 *值* 的类型为 **`long long`**

- `L"%llu"` 如果 *值* 的类型为 **`unsigned long long`**

- `L"%f"` 如果 *值* 的类型为 **`float`** 或 **`double`**

- `L"%Lf"` 如果 *值* 的类型为 **`long double`**

该函数返回 `wstring(Buf)`。

## <a name="see-also"></a>请参阅

[\<string>](../standard-library/string.md)
