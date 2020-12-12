---
description: 了解详细信息： &lt; span &gt; 函数
title: '&lt;跨度 &gt; 函数'
ms.date: 05/28/2020
f1_keywords:
- span/std::span::as_bytes
- span/std::as_writable_bytes
helpviewer_keywords:
- std::span [C++], as_writable_bytes
- std::as_bytes [C++]
ms.openlocfilehash: 09d712d6dfffee2aa24e0e8cecca4031a27923f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169185"
---
# <a name="ltspangt-functions"></a>&lt;跨度 &gt; 函数

\<span>标头包含对 **span** 对象执行的下列非成员函数。

| **非成员函数** | **说明** |
|-|-|
|[as_bytes](#as_bytes) | 获取范围中元素的对象表示形式的只读视图。 |
|[as_writable_bytes](#as_writable_bytes) | 获取范围中元素的对象表示形式的读/写视图。 |

## <a name="as_bytes"></a>`as_bytes`

获取范围中元素的对象表示形式的只读视图。

```cpp
template <class T, size_t Extent>
auto as_bytes(span<T, Extent> s) noexcept;
```

### <a name="parameters"></a>parameters

*关心*\
范围中元素的类型。

*范围*\
如果编译时) ，则跨度中的元素数 (; 否则， `dynamic_extent` 表示在运行时之前不会知道元素的数目。

*些*\
要获取其原始表示形式的范围。

### <a name="return-value"></a>返回值

一个 `span<const byte, S>` 指向存储在中的第一个项的 `S` ，其中 `{reinterpret_cast<const std::byte*>(s.data()), s.size_bytes()}`

### <a name="example"></a>示例

```cpp
#include <span>
#include <iostream>

using namespace std;

void main()
{
    int a[] = { 0,1,2 };
    span <int> mySpan(a);
    auto bytes = std::as_bytes(mySpan);
}
```

## <a name="as_writable_bytes"></a>`as_writable_bytes`

如果 `T` 不是 **`const`** ，则获取范围中元素的原始字节表示形式的读/写视图。

```cpp
template <class T, size_t Extent>
auto as_writable_bytes(span<T, Extent> s) noexcept;
```

### <a name="parameters"></a>parameters

*关心*\
范围中元素的类型。

*范围*\
如果编译时) ，则跨度中的元素数 (; 否则， `dynamic_extent` 表示在运行时之前不会知道元素的数目。

*些*\
要获取其原始表示形式的范围。

### <a name="return-value"></a>返回值

一个 `span<byte, S>` 指向存储在中的第一个项的 `S` ，其中 `{reinterpret_cast<std::byte*>(s.data()), s.size_bytes()}`

### <a name="example"></a>示例

```cpp
#include <span>
#include <iostream>

using namespace std;

void main()
{
    int a[] = { 0,1,2 };
    span <int> mySpan(a);
    auto bytes = as_writable_bytes(mySpan);
}
```

## <a name="see-also"></a>请参阅

[\<span>](span.md)
