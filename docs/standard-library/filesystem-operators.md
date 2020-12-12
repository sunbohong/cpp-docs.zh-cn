---
description: 了解详细信息： &lt; filesystem &gt; 运算符
title: '&lt;filesystem&gt; 运算符'
ms.date: 11/04/2016
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::operator==
- FILESYSTEM/std::experimental::filesystem::operator!=
- FILESYSTEM/std::experimental::filesystem::operator<
- FILESYSTEM/std::experimental::filesystem::operator<=
- FILESYSTEM/std::experimental::filesystem::operator>
- FILESYSTEM/std::experimental::filesystem::operator>=
- FILESYSTEM/std::experimental::filesystem::operator/
- FILESYSTEM/std::experimental::filesystem::operator<<
- FILESYSTEM/std::experimental::filesystem::operator>>
ms.assetid: 102c4833-aa3b-41a8-8998-f5003c546bfd
ms.openlocfilehash: 140ef553cbfd17fe2b1cfc41bedba397506da817
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232456"
---
# <a name="ltfilesystemgt-operators"></a>&lt;filesystem&gt; 运算符

这些运算符将两个路径作为字符串进行词汇比较。 使用 `equivalent` 函数来确定是否 (两个路径（例如，相对路径和绝对路径）) 引用磁盘上的同一文件或目录。

有关详细信息，请参阅[文件系统导航 (C++)](../standard-library/file-system-navigation.md)。

## <a name="operator"></a>operator==

```cpp
bool operator==(const path& left, const path& right) noexcept;
```

函数返回 left.native() == right.native()。

## <a name="operator"></a>operator!=

```cpp
bool operator!=(const path& left, const path& right) noexcept;
```

函数返回 !(left == right)。

## <a name="operator"></a>operator<

```cpp
bool operator<(const path& left, const path& right) noexcept;
```

函数返回 left.native() < right.native()。

## <a name="operator"></a>operator<=

```cpp
bool operator<=(const path& left, const path& right) noexcept;
```

函数返回 !(right \< left)。

## <a name="operator"></a>operator>

```cpp
bool operator>(const path& left, const path& right) noexcept;
```

函数返回 right \< left。

## <a name="operator"></a>operator>=

```cpp
bool operator>=(const path& left, const path& right) noexcept;
```

函数返回 !(left < right)。

## <a name="operator"></a>operator/

```cpp
path operator/(const path& left, const path& right);
```

函数执行：

```cpp
basic_string<Elem, Traits> str;
path ans = left;
return (ans /= right);
```

## <a name="operator"></a>operator<<

```cpp
template <class Elem, class Traits>
basic_ostream<Elem, Traits>& operator<<(basic_ostream<Elem, Traits>& os, const path& pval);
```

该函数返回 os << pval \<Elem, Traits> ( # A1。

## <a name="operator"></a>operator>>

```cpp
template <class Elem, class Traits>
basic_istream<Elem, Traits>& operator<<(basic_istream<Elem, Traits>& is, const path& pval);
```

函数执行：

```cpp
basic_string<Elem, Traits> str;
is>> str;
pval = str;
return (is);
```
