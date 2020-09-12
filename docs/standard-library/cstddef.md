---
title: '&lt;cstddef&gt;'
description: 介绍 <stddef.h>，它可确保在命名空间中声明使用 C 标准库标头中的外部链接声明的名称 `std` 。
ms.date: 9/4/2020
f1_keywords:
- <cstddef>
helpviewer_keywords:
- cstddef header
ms.assetid: be8d1e39-5974-41ee-b41d-eafa6c82ffce
ms.openlocfilehash: 186de0e893c413a25d31d4f1431c280d749e9541
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040023"
---
# <a name="ltcstddefgt"></a>&lt;cstddef&gt;

包括 C 标准库标头 \<stddef.h> 并将关联名称添加到 `std` 命名空间。 包括此标头可确保在命名空间中声明使用 C 标准库标头中的外部链接声明的名称 `std` 。

> [!NOTE]
> \<cstddef> 包括类型 **byte** ，不包括类型 **`wchar_t`** 。

## <a name="syntax"></a>语法

```cpp
#include <cstddef>
```

## <a name="namespace-and-macros"></a>命名空间和宏

```cpp
namespace std {
    using ptrdiff_t = see definition;
    using size_t = see definition;
    using max_align_t = see definition;
    using nullptr_t = decltype(nullptr);
}

#define NULL  // an implementation-defined null pointer constant
#define offsetof(type, member-designator)
```

### <a name="parameters"></a>参数

*ptrdiff_t*\
实现定义的有符号整数类型，它可以保存数组对象中两个下标的差。

*size_t*\
实现定义的无符号整数类型，该类型足够大，足以包含任何对象的大小（以字节为单位）。

*max_align_t*\
一个 POD 类型，其对齐要求至少与每个标量类型的类型相同，并且每个上下文都支持其对齐要求。

*nullptr_t*\
表达式的类型的同义词 **`nullptr`** 。 尽管 **`nullptr`** 无法采用地址，但也可以采用作为左值的另一个 *nullptr_t* 对象的地址。

## <a name="byte-class"></a>byte 类

```cpp
enum class byte : unsigned char {};

template <class IntType>
    constexpr byte& operator<<=(byte& b, IntType shift) noexcept;
    constexpr byte operator<<(byte b, IntType shift) noexcept;
    constexpr byte& operator>>=(byte& b, IntType shift) noexcept;
    constexpr byte operator>>(byte b, IntType shift) noexcept;

constexpr byte& operator|=(byte& left, byte right) noexcept;
constexpr byte operator|(byte left, byte right) noexcept;
constexpr byte& operator&=(byte& left, byte right) noexcept;
constexpr byte operator&(byte left, byte right) noexcept;
constexpr byte& operator^=(byte& left, byte right) noexcept;
constexpr byte operator^(byte left, byte right) noexcept;
constexpr byte operator~(byte b) noexcept;

template <class IntType>
    IntType to_integer(byte b) noexcept;
```

## <a name="see-also"></a>另请参阅

[标头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[C + + 标准库概述](../standard-library/cpp-standard-library-overview.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
