---
description: '了解详细信息：标点符号 (c + +) '
title: 标点符号 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- punctuators [C++]
ms.assetid: 1521564c-a977-488a-9490-068079897592
ms.openlocfilehash: 7485ea82725c2221d32d0647123cfce473719ca3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319425"
---
# <a name="punctuators-c"></a>标点符号 (C++)

在 C++ 中，标点符号相对于编译器来说具有语法意义和语义含义，但是它们本身不会指定一个产生数值的操作。 某些标点符号（单独或组合）也可以是 C++ 运算符或对预处理器很重要。

以下任意字符都被视为标点符号：

```
! % ^ & * ( ) - + = { } | ~
[ ] \ ; ' : " < > ? , . / #
```

[翻译阶段](../preprocessor/phases-of-translation.md)4 后，标点符号 **[]**、 **( )** 和 **{}** 必须成对出现。

## <a name="see-also"></a>请参阅

[词法约定](../cpp/lexical-conventions.md)
