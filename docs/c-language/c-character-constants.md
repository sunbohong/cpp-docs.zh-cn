---
description: 详细了解：C 字符常量
title: C 字符常量
ms.date: 11/04/2016
helpviewer_keywords:
- characters, constants
- (') single quotation mark
- constants, character
- single quotation mark
ms.assetid: 388ae7d7-2c3a-44d6-a507-63f541ecd2da
ms.openlocfilehash: 2503fc983d79f363f525b22172d2113393b41091
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211552"
---
# <a name="c-character-constants"></a>C 字符常量

“字符常量”通过在单引号 (' '  ) 内封闭可表示的字符集中的单个字符来构成。 字符常量用于表示[执行字符集](../c-language/execution-character-set.md)内的字符。

## <a name="syntax"></a>语法

*character-constant*: **'** *c-char-sequence* **'**

**L'** *c-char-sequence* **'**

*c-char-sequence*: *c-char*

*c-char-sequence c-char*

*c-char*:除单引号 ('  )、反斜杠 (\\  ) 或者换行符以外的所有源字符集成员

escape-sequence 

*escape-sequence*: *simple-escape-sequence*

*octal-escape-sequence*

*hexadecimal-escape-sequence*

*simple-escape-sequence*: one of **\a \b \f \n \r \t \v**

**\\' \\" \\\ \\?**

*octal-escape-sequence*: **\\**  *octal-digit*

**\\**  *octal-digit octal-digit*

**\\**  *octal-digit octal-digit octal-digit*

*hexadecimal-escape-sequence*: **\x**  *hexadecimal-digit*

*hexadecimal-escape-sequence hexadecimal-digit*

## <a name="see-also"></a>请参阅

[C 常量](../c-language/c-constants.md)
