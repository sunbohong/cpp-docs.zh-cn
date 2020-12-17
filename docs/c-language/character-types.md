---
description: 详细了解：字符类型
title: 字符类型
ms.date: 11/04/2016
helpviewer_keywords:
- character data types [C]
- types [C], character
ms.assetid: d3ca8cda-c0d7-43af-9472-697e8ef015ce
ms.openlocfilehash: 270c1831422d81fe88519a2aee3de8306727d0d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293529"
---
# <a name="character-types"></a>字符类型

前面没有字母 L 的整型字符常数的类型为 `int`。 包含单个字符的整数字符常量的值是解释为整数的字符的数字值。 例如，字符 `a` 的数字值在十进制和十六进制下分别为 97 和 61。

从语法上来说，“宽字符常量”是带有字母 L 前缀的字符常量。宽字符常数的类型为 `wchar_t`（在 STDDEF.H 头文件中定义的整型类型）。 例如：

```
char    schar =  'x';   /* A character constant          */
wchar_t wchar = L'x';   /* A wide-character constant for
                            the same character           */
```

宽字符常量的宽度为 16 位，用于指定扩展执行字符集的成员。 借助它们，可以用字母表示因太大而无法用类型 `char` 表示的字符。 有关宽字符的详细信息，请参阅[多字节和宽字符](../c-language/multibyte-and-wide-characters.md)。

## <a name="see-also"></a>请参阅

[C 字符常量](../c-language/c-character-constants.md)
