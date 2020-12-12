---
description: 了解详细信息： Null 语句
title: Null 语句
ms.date: 11/04/2016
helpviewer_keywords:
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 606f5953-55f0-40c8-ae03-3ee3a819b851
ms.openlocfilehash: 1aa488da395cf84ae9ef6d78939f1f1e3019c572
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146167"
---
# <a name="null-statement"></a>Null 语句

"Null 语句" 是缺少 *表达式* 的表达式语句。 当语言的语法调用语句而不是表达式计算时，它很有用。   它包括分号。

Null 语句通常用作迭代语句中的占位符或用作在复合语句或函数的末尾放置标签的语句。

以下代码片段说明如何将一个字符串复制到另一个字符串，并包含 null 语句：

```cpp
// null_statement.cpp
char *myStrCpy( char *Dest, const char *Source )
{
    char *DestStart = Dest;

    // Assign value pointed to by Source to
    // Dest until the end-of-string 0 is
    // encountered.
    while( *Dest++ = *Source++ )
        ;   // Null statement.

    return DestStart;
}

int main()
{
}
```

## <a name="see-also"></a>请参阅

[Expression 语句](../cpp/expression-statement.md)
