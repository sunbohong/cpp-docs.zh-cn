---
description: 了解详细信息： char_traits &lt; char &gt; Struct
title: char_traits&lt;char&gt; 结构
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::char_traits<char>
- char_traits<char >
helpviewer_keywords:
- char_traits<char> class
ms.assetid: abd9373a-77db-4031-bf4b-f8ac15087581
ms.openlocfilehash: 67a4cc5291445210f2cf384ca556e6e55fcfe15e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234288"
---
# <a name="char_traitsltchargt-struct"></a>char_traits&lt;char&gt; 结构

作为模板结构的专用化的结构，该 **结构 \<CharType> char_traits** 类型为的元素 **`char`** 。

## <a name="syntax"></a>语法

```cpp
template <>
struct char_traits<char>;
```

## <a name="remarks"></a>备注

专用化允许结构利用操作此类型对象的库函数 **`char`** 。

## <a name="example"></a>示例

请参阅类模板[Char_traits 类](../standard-library/char-traits-struct.md)的 typedef 和成员函数
