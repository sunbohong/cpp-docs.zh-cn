---
description: 了解详细信息： &lt; 可选 &gt; 函数
title: '&lt;可选 &gt; 函数'
ms.date: 11/04/2016
f1_keywords:
- optional/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: d48329005b24b96a12a95e1d895319796bd41928
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201906"
---
# <a name="ltoptionalgt-functions"></a>&lt;可选 &gt; 函数

## <a name="make_optional"></a><a name="make_optional"></a> make_optional

使对象成为可选的。

```cpp
template <class T>
    constexpr optional<see below> make_optional(T&&);
template <class T, class... Args>
    constexpr optional<T> make_optional(Args&&... args);
template <class T, class U, class... Args>
    constexpr optional<T> make_optional(initializer_list<U> il, Args&&... args);
```

## <a name="nullopt"></a><a name="nullopt"></a> nullopt

```cpp
inline constexpr nullopt_t nullopt(unspecified );
```

## <a name="swap"></a><a name="swap"></a> 购

```cpp
template <class T>
    void swap(optional<T>&, optional<T>&) noexcept(see below );
```
