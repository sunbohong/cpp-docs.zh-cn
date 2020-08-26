---
title: '&lt;ostream&gt; 函数'
ms.date: 11/04/2016
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.openlocfilehash: 4db966797202b16911aa67b6fda7c81785d98166
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842632"
---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt; 函数

这些是在 ostream 中定义的全局模板函数 &lt; &gt; 。 有关成员函数的详细说明，请参阅 [Basic_ostream 类](basic-ostream-class.md) 文档。

[endl](#endl)\
[结尾](#ends)\
[平](#flush)\
[swap](#swap)

## <a name="endl"></a>endl

终止行并刷新缓冲区。

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& endl(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>参数

*Elem*\
元素类型。

*Ostr*\
**Basic_ostream**类型的对象。

*Tr*\
字符特征。

### <a name="return-value"></a>返回值

**Basic_ostream**类型的对象。

### <a name="remarks"></a>注解

操控器调用 *Ostr*。[ (](../standard-library/basic-ostream-class.md#put) *Ostr*。[扩大](../standard-library/basic-ios-class.md#widen) ( "\n" ) # A3，然后调用 *Ostr*。[flush](../standard-library/basic-ostream-class.md#flush)。 它将返回 *Ostr*。

### <a name="example"></a>示例

```cpp
// ostream_endl.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << endl;
}
```

```Output
testing
```

## <a name="ends"></a>结尾

终止字符串。

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& ends(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>参数

*Elem*\
元素类型。

*Ostr*\
一个 `basic_ostream` 类型的对象。

*Tr*\
字符特征。

### <a name="return-value"></a>返回值

一个 `basic_ostream` 类型的对象。

### <a name="remarks"></a>注解

操控器调用 *Ostr*。[将](../standard-library/basic-ostream-class.md#put) (*Elem* ( "\ 0" ) # A3。 它将返回 *Ostr*。

### <a name="example"></a>示例

```cpp
// ostream_ends.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "a";
   cout << "b" << ends;
   cout << "c" << endl;
}
```

```Output
ab c
```

## <a name="flush"></a>flush

刷新缓冲区。

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& flush(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>参数

*Elem*\
元素类型。

*Ostr*\
一个 `basic_ostream` 类型的对象。

*Tr*\
字符特征。

### <a name="return-value"></a>返回值

一个 `basic_ostream` 类型的对象。

### <a name="remarks"></a>注解

操控器调用 *Ostr*。[flush](../standard-library/basic-ostream-class.md#flush)。 它将返回 *Ostr*。

### <a name="example"></a>示例

```cpp
// ostream_flush.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << flush;
}
```

```Output
testing
```

## <a name="swap"></a>swap

交换两个 `basic_ostream` 对象的值。

```cpp
template <class Elem, class Tr>
void swap(
   basic_ostream<Elem, Tr>& left,
   basic_ostream<Elem, Tr>& right);
```

### <a name="parameters"></a>参数

*Elem*\
元素类型。

*Tr*\
字符特征。

*左中*\
对 `basic_ostream` 对象的左值引用。

*然后*\
对 `basic_ostream` 对象的左值引用。

### <a name="remarks"></a>注解

模板函数 `swap` 执行 `left.swap(right)`。

## <a name="see-also"></a>另请参阅

[\<ostream>](../standard-library/ostream.md)
