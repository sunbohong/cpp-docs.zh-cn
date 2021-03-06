---
description: 了解详细信息： scanf 类型字段字符
title: scanf 类型字段字符
ms.date: 11/04/2016
helpviewer_keywords:
- scanf function, type field characters
ms.assetid: 5d546a84-715b-44ca-b1c5-bbe997f9ff62
ms.openlocfilehash: 5a98b65b3c4e236a637d0e50c26c998e77657f31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273613"
---
# <a name="scanf-type-field-characters"></a>scanf 类型字段字符

以下信息适用于函数的所有 `scanf` 系列，包括 `scanf_s`等安全版本。

`type` 字符是唯一必需的格式字段；它显示在任何可选格式字段的后面。 `type` 字符决定了关联的自变量是解释为字符、字符串还是数字。

### <a name="type-characters-for-scanf-functions"></a>scanf 函数的类型字符

|字符|预期输入类型|参数类型|安全版本中的大小参数？|
|---------------|----------------------------|----------------------|--------------------------------------|
|`c`|字符。 与 `scanf` 函数结合使用时，指定单字节字符；与 `wscanf` 函数结合使用时，指定宽字符。 指定了 `c` 时，也会读取通常被跳过的空白字符。 若要读取下一个非空白单字节字符，请使用 `%1s`；若要读取下一个非空白宽字符，请使用 `%1ws`。|**`char`** 与函数结合使用时，指向与函数一起使用 `scanf` 时的指针 **`wchar_t`** `wscanf` 。|必需。 大小中不包括 null 终止符的占用空间。|
|`C`|相反大小字符。 与 `scanf` 函数结合使用时，指定宽字符；与 `wscanf` 函数结合使用时，指定单字节字符。 指定了 `C` 时，也会读取通常被跳过的空白字符。 若要读取下一个非空白单字节字符，请使用 `%1s`；若要读取下一个非空白宽字符，请使用 `%1ws`。|**`wchar_t`** 与函数结合使用时，指向与函数一起使用 `scanf` 时的指针 **`char`** `wscanf` 。|必需。 大小参数不包括 null 终止符的占用空间。|
|`d`|十进制整数。|指向 **`int`** 的指针。|错误。|
|`i`|一个整数。 如果输入字符串以“0x”或“0X”开始，则为十六进制；如果字符串以“0”开始，则为八进制；其余情况为十进制。|指向 **`int`** 的指针。|错误。|
|`o`|八进制整数。|指向 **`int`** 的指针。|错误。|
|`p`|十六进制数字中的指针地址。 最大位数读数取决于指针大小（32 或 64 位），指针大小取决于计算机体系结构。 接受“0x”或“0X”作为前缀。|指向 **`void*`** 的指针。|错误。|
|`u`|无符号十进制整数。|指向 **`unsigned int`** 的指针。|错误。|
|`x`|十六进制整数。|指向 **`int`** 的指针。|错误。|
|`e`, `E`, `f`, `F`, `g`, `G`|包含可选符号（+ 或 -）的浮点值、包含小数点的一个或多个十进制数字系列，以及后跟可选带符号整数值的可选指数（“e”或“E”）。|指向 **`float`** 的指针。|错误。|
|`a`, `A`|由一系列一个或多个包含可选小数点的十六进制数字和后跟十进制值的一个指数（“p”或“P”）所组成的浮点值。|指向 **`float`** 的指针。|错误。|
|`n`|未从流或缓冲区读取任何输入。|指向的指针 **`int`** ，其中存储的字符数在当前调用 `scanf` 函数或函数时从流或缓冲区到该点成功读取的字符数 `wscanf` 。|错误。|
|`s`|字符串，直到第一个空白字符（空格、制表符或换行）。 若要读取未被空格字符分隔的字符串，请使用一组方括号 (`[ ]`)，如 [scanf 宽度规范](../c-runtime-library/scanf-width-specification.md)中所述。|与 `scanf` 函数结合使用时，表示单字节字符数组；与 `wscanf` 函数结合使用时，表示宽字符数组。 无论哪种情况，字符数组都必须具有足够大小以容纳输入字段和自动附加的终止 null 字符。|必需。 大小中包括 null 终止符的占用空间。|
|`S`|相反大小字符字符串，直到第一个空白字符（空格、制表符或换行）。 若要读取未被空格字符分隔的字符串，请使用一组方括号 (`[ ]`)，如 [scanf 宽度规范](../c-runtime-library/scanf-width-specification.md)中所述。|与 `scanf` 函数结合使用时，表示宽字符数组；与 `wscanf` 函数结合使用时，表示单字节字符数组。 无论哪种情况，字符数组都必须具有足够大小以容纳输入字段和自动附加的终止 null 字符。|必需。 大小中包括 null 终止符的占用空间。|

大小参数（如需要）应紧跟在其适用于的参数之后传递到参数列表中。 例如，以下代码：

```
char string1[11], string2[9];
scanf_s("%10s %8s", string1, 11, string2, 9);
```

将最大长度为 10 的字符串读入 `string1`，并将最大长度为 8 的字符串读入 `string2`。 缓冲区大小应至少比宽度规范多一个，因为必须为 null 终止符保留空间。

无论是使用函数的单字节字符版本还是宽字符版本，格式字符串都可以处理单字节或宽字符输入。 因此，若要读取包含 `scanf` 函数和 `wscanf` 函数的单字节字符或宽字符，请按如下所述使用格式说明符。

|若要将字符读取为|使用此函数|使用这些格式说明符|
|--------------------------|-----------------------|----------------------------------|
|单字节|`scanf` 函数|`c`、`hc` 或 `hC`|
|单字节|`wscanf` 函数|`C`、`hc` 或 `hC`|
|宽|`wscanf` 函数|`c`、`lc` 或 `lC`|
|宽|`scanf` 函数|`C`、`lc` 或 `lC`|

若要扫描包含 `scanf` 函数和 `wscanf` 函数的字符串，请将上表与格式类型说明符 `s` 和 `S` 结合使用，而不是与 `c` 和 `C`一起使用。

## <a name="see-also"></a>请参阅

[scanf、_scanf_l、wscanf、_wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)
