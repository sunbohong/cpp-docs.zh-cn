---
description: 了解详细信息： basic_istringstream 类
title: basic_istringstream 类
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_istringstream
- sstream/std::basic_istringstream::allocator_type
- sstream/std::basic_istringstream::rdbuf
- sstream/std::basic_istringstream::str
- sstream/std::basic_istringstream::swap
helpviewer_keywords:
- std::basic_istringstream [C++]
- std::basic_istringstream [C++], allocator_type
- std::basic_istringstream [C++], rdbuf
- std::basic_istringstream [C++], str
- std::basic_istringstream [C++], swap
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
ms.openlocfilehash: 34073c660b5ede3d7df54e9e067ef5c3963671f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325675"
---
# <a name="basic_istringstream-class"></a>basic_istringstream 类

描述一个对象，该对象控制从类 [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **Elem**、 **Tr**> 的流缓冲区中提取元素和编码对象 `Alloc` 。

## <a name="syntax"></a>语法

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_istringstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>parameters

*分配*\
allocator 类。

*Elem*\
字符串的基本元素的类型。

*Tr*\
字符串的基本元素上专用的字符特征。

## <a name="remarks"></a>备注

类模板描述了一个对象，该对象控制从类 [basic_stringbuf](../standard-library/basic-stringbuf-class.md)Elem，Tr，> 的流缓冲区提取元素和编码对象， <    `Alloc` 其字符特征由类 *Tr* 确定，其元素由类 *分配* 的分配器进行分配。 该对象存储 basic_stringbuf< **Elem**, **Tr**, `Alloc`> 类的对象。

### <a name="constructors"></a>构造函数

|构造函数|说明|
|-|-|
|[basic_istringstream](#basic_istringstream)|构造 `basic_istringstream` 类型的对象。|

### <a name="typedefs"></a>Typedef

|类型名称|描述|
|-|-|
|[allocator_type](#allocator_type)|类型是模板参数 `Alloc` 的同义词。|

### <a name="member-functions"></a>成员函数

|成员函数|说明|
|-|-|
|[rdbuf](#rdbuf)|将类型的已存储流缓冲区的地址返回 `pointer` 到[basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem` 、 `Tr` `Alloc`>。|
|[str](#str)|设置或获取字符串缓冲区中的文本，而无需更改写入位置。|
|[swap](#swap)|将此 `basic_istringstream` 对象中的值与所提供对象的值进行交换。|

### <a name="operators"></a>运算符

|运算符|描述|
|-|-|
|[operator =](#op_eq)|将值从对象参数赋给此 `basic_istringstream` 对象。|

## <a name="requirements"></a>要求

**标头：**\<sstream>

**命名空间:** std

## <a name="basic_istringstreamallocator_type"></a><a name="allocator_type"></a> basic_istringstream：： allocator_type

类型是模板参数 `Alloc` 的同义词。

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_istringstreambasic_istringstream"></a><a name="basic_istringstream"></a> basic_istringstream：： basic_istringstream

构造 `basic_istringstream` 类型的对象。

```cpp
explicit basic_istringstream(
    ios_base::openmode _Mode = ios_base::in);

explicit basic_istringstream(
    const basic_string<Elem, Tr, Alloc>& str,
    ios_base::openmode _Mode = ios_base::in);

basic_istringstream(
    basic_istringstream&& right);
```

### <a name="parameters"></a>parameters

*_Mode*\
[ios_base::openmode](../standard-library/ios-base-class.md#openmode) 中的枚举之一。

*字符串*\
一个 `basic_string` 类型的对象。

*然后*\
`basic_istringstream` 对象的右值引用。

### <a name="remarks"></a>备注

第一个构造函数通过调用[basic_istream](../standard-library/basic-istream-class.md) (`sb`) （其中 `sb` 是类[basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem` 、 `Tr` 、> 的存储对象）来初始化基类 `Alloc` 。 通过调用 `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `_Mode` &#124; `ios_base::in`)，它还可以初始化 `sb`。

第二个构造函数通过调用 `basic_istream(sb)` 初始化基类。 通过调用 `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `str`, `_Mode` &#124; `ios_base::in`)，它还可以初始化 `sb`。

第三个构造函数使用 *右侧* 的内容来初始化对象，该对象被视为右值引用。

## <a name="basic_istringstreamoperator"></a><a name="op_eq"></a> basic_istringstream：： operator =

将值从对象参数赋给此 `basic_istringstream` 对象。

```cpp
basic_istringstream& operator=(basic_istringstream&& right);
```

### <a name="parameters"></a>parameters

*然后*\
对 `basic_istringstream` 对象的右值引用。

### <a name="remarks"></a>备注

成员运算符将对象的内容替换为 *右侧* 的内容，被视为右值引用移动赋值。

## <a name="basic_istringstreamrdbuf"></a><a name="rdbuf"></a> basic_istringstream：： rdbuf

将类型的已存储流缓冲区的地址返回 `pointer` [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  **Elem**， **Tr**， `Alloc`>。

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>返回值

`pointer`要 basic_stringbuf< **Elem**， **Tr**，> 类型的已存储流缓冲区的地址 `Alloc` 。

### <a name="example"></a>示例

有关如何使用 `rdbuf` 的示例，请参阅 [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close)。

## <a name="basic_istringstreamstr"></a><a name="str"></a> basic_istringstream：： str

设置或获取字符串缓冲区中的文本，而无需更改写入位置。

```cpp
basic_string<Elem, Tr, Alloc> str() const;

void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>parameters

*_Newstr*\
新字符串。

### <a name="return-value"></a>返回值

返回类 [basic_string](../standard-library/basic-string-class.md) <  **Elem**， **Tr**，> 的对象 `Alloc` ，其受控序列是 **\* 此** 控制的序列的副本。

### <a name="remarks"></a>备注

第一个成员函数返回[rdbuf](#rdbuf)  ->  [str](../standard-library/basic-stringbuf-class.md#str)。 第二个成员函数 `rdbuf`  -> ) 调用 **str** ( `_Newstr` 。

### <a name="example"></a>示例

有关使用的示例，请参阅 [basic_stringbuf：： str](../standard-library/basic-stringbuf-class.md#str) `str` 。

## <a name="basic_istringstreamswap"></a><a name="swap"></a> basic_istringstream：： swap

交换两个 `basic_istringstream` 对象的值。

```cpp
void swap(basic_istringstream& right);
```

### <a name="parameters"></a>parameters

*然后*\
对 `basic_istringstream` 对象的左值引用。

### <a name="remarks"></a>备注

该成员函数将交换此对象的值和 *权限* 的值。

## <a name="see-also"></a>请参阅

[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream 编程](../standard-library/iostream-programming.md)\
[iostreams 约定](../standard-library/iostreams-conventions.md)
