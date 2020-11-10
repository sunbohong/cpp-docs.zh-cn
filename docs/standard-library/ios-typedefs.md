---
title: '`<ios>` typedef'
description: 描述 `<ios>` 支持 `ios` 旧库中的类的 c + + 标准模板库 (STL) typedef `iostream` 。
ms.date: 11/06/2020
f1_keywords:
- iosfwd/std::ios
- iosfwd/std::streamoff
- iosfwd/std::streampos
- iosfwd/std::streamsize
- iosfwd/std::wios
- iosfwd/std::wstreampos
ms.openlocfilehash: b9dbed64c88a00f5ca065e23c4af2f3922634ece
ms.sourcegitcommit: b38485bb3a9d479e0c5d64ffc3d841fa2c2b366f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441263"
---
# <a name="ios-typedefs"></a>`<ios>` typedef

## `ios`

支持 `ios` 旧库中的类 `iostream` 。

```cpp
typedef basic_ios<char, char_traits<char>> ios;
```

### <a name="remarks"></a>备注

类型是类模板的同义词 [`basic_ios`](../standard-library/basic-ios-class.md) ，专用于 **`char`** 具有默认字符特征的类型的元素。

## `streamoff`

支持内部操作。

```cpp
#ifdef _WIN64
    typedef __int64 streamoff;
#else
    typedef long streamoff;
#endif
```

### <a name="remarks"></a>备注

类型为带符号整数。 它描述可在流定位操作中存储字节偏移量的对象。 它的表示形式具有至少 32 个值位。 这并不一定足以表示流中的任意字节位置。 该值 `streamoff(-1)` 通常指示错误的偏移量。

## `streampos`

保留缓冲区指针或文件指针的当前位置。

```cpp
typedef fpos<mbstate_t> streampos;
```

### <a name="remarks"></a>备注

该类型是> 的同义词 [`fpos`](../standard-library/fpos-class.md) <  `mbstate_t` 。

### <a name="example"></a>示例

```cpp
// ios_streampos.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;

   ofstream x( "iostream.txt" );
   x << "testing";
   streampos y = x.tellp( );
   cout << streamoff( y ) << '\n';
}
```

```Output
7
```

## `streamsize`

表示流的大小。

```cpp
#ifdef _WIN64
    typedef __int64 streamsize;
#else
    typedef int streamsize;
#endif
```

### <a name="remarks"></a>备注

此类型为带符号整数，该整数描述的对象可存储多个流操作涉及的元素数量计数。 它的表示形式具有至少 16 个值位。 这并不一定足以表示流中的任意字节位置。

### <a name="example"></a>示例

编译并运行以下程序之后，查看文件 `test.txt` 以查看设置的效果 `streamsize` 。

```cpp
// ios_streamsize.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   char a[16] = "any such text";
   ofstream x( "test.txt" );
   streamsize y = 6;
   x.write( a, y );
}
```

## `wios`

支持 `wios` 旧库中的类 `iostream` 。

```cpp
typedef basic_ios<wchar_t, char_traits<wchar_t>> wios;
```

### <a name="remarks"></a>备注

类型是类模板的同义词 [`basic_ios`](../standard-library/basic-ios-class.md) ，专用于 **`wchar_t`** 具有默认字符特征的类型的元素。

## `wstreampos`

保留缓冲区指针或文件指针的当前位置。

```cpp
typedef fpos<mbstate_t> wstreampos;
```

### <a name="remarks"></a>备注

该类型是> 的同义词 [`fpos`](../standard-library/fpos-class.md) <  `mbstate_t` 。

### <a name="example"></a>示例

```cpp
// ios_wstreampos.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   wofstream xw( "wiostream.txt" );
   xw << L"testing";
   wstreampos y = xw.tellp( );
   cout << streamoff( y ) << '\n';
}
```

```Output
7
```
