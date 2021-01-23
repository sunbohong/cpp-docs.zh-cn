---
title: 预处理器语法摘要 (C/C++)
description: 定义并描述 Microsoft C/c + + 编译器 (MSVC) 预处理器语法语法。
ms.date: 01/22/2021
helpviewer_keywords:
- grammar
- preprocessor, grammar
ms.openlocfilehash: dbe46a67337bf55cb98100878dedb8c92120472b
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713631"
---
# <a name="preprocessor-grammar-summary-cc"></a>预处理器语法摘要 (C/C++)

本文介绍 C 和 c + + 预处理器的正式语法。 其中包含预处理指令和运算符的语法。 有关详细信息，请参阅 [预处理器](../preprocessor/preprocessor.md) 和 [杂注指令以及 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)。

## <a name="definitions-for-the-grammar-summary"></a><a name="definitions"></a> 语法摘要的定义

终止符是语法定义中的终结点。 不提供其他解决方法。 终止符包括保留字和用户定义的标识符的集。

非终止符是语法中的占位符。 它们中的大多数是在此语法摘要中的其他位置定义的。 定义可是递归的。 以下非终止符在 *c + + 语言参考* 的 "[词法约定](../cpp/lexical-conventions.md)" 部分中定义：

*`constant`*, *`constant-expression`*, *`identifier`*, *`keyword`*, *`operator`*, *`punctuator`*

可选组件由带下标的 <sub>opt</sub> 指示。 例如，下面的语法指示括在大括号中的可选表达式：

**`{`***`expression`* <sub>opt</sub>**`}`**

## <a name="document-conventions"></a><a name="conventions"></a> 文档约定

约定将对不同的语法组件使用不同的字体特性。 符号和字体如下所示：

| 特性 | 说明 |
|---------------|-----------------|
| *`nonterminal`* | 斜体类型指示非终止符。 |
| **`#include`** | 粗体类型的终止符是必须按所示方式输入的文本保留字和符号。 此上下文中的字符始终区分大小写。 |
| <sub>opt</sub> | 后跟 <sub>opt </sub> 的非终止符始终是可选的。|
| default typeface | 用此字样描述或列出的集中的字符可在语句中用作终止符。 |

**`:`** 非终止符后面) 的冒号 (引入了其定义。 替代定义在单独的行上列出。

在代码语法块中，默认字样中的这些符号具有特殊含义：

| 符号 | 说明 |
|---|---|
| \[ ] | 方括号括起一个可选元素。 |
| { \| } | 大括号环绕替代元素，用竖线分隔。 |
| ... | 指示上一个元素模式可以重复。 |

在代码语法块中，逗号 (`,`) 、句点 (`.`) 、分号 () `;` 、冒号 () `:` 、括号 (`( )`) 、双引号 () `"` 和单引号 () `'` 是文本。

## <a name="preprocessor-grammar"></a><a name="grammar"></a> 预处理器语法

*`control-line`*:\
&emsp;**`#define`***`identifier`* *`token-string`* <sub>opt</sub>\
&emsp;**`#define`***`identifier`* **`(`** *`identifier`*<sub>opt</sub> **`,`**... **`,`***`identifier`* <sub></sub> **`)`** opt *`token-string`*<sub>opt</sub>\
&emsp;**`#include`** **`"`**_`path-spec`_**`"`**\
&emsp;**`#include`** **`<`**_`path-spec`_**`>`**\
&emsp;**`#line`***`digit-sequence`* **`"`**_`filename`_**`"`**<sub>opt</sub>\
&emsp;**`#undef`** *`identifier`*\
&emsp;**`#error`** *`token-string`*\
&emsp;**`#pragma`** *`token-string`*

*`constant-expression`*:\
&emsp;**`defined(`** *`identifier`* **`)`**\
&emsp;**`defined`** *`identifier`*\
&emsp;任何其他常数表达式

*`conditional`*:\
&emsp; *`if-part`* *`elif-parts`* <sub>opt</sub> *`else-part`* <sub>opt</sub> *`endif-line`*

*`if-part`*:\
&emsp;*`if-line`* *`text`*

*`if-line`*:\
&emsp;**`#if`** *`constant-expression`*\
&emsp;**`#ifdef`** *`identifier`*\
&emsp;**`#ifndef`** *`identifier`*

*`elif-parts`*:\
&emsp;*`elif-line`* *`text`*\
&emsp;*`elif-parts`* *`elif-line`* *`text`*

*`elif-line`*:\
&emsp;**`#elif`** *`constant-expression`*

*`else-part`*:\
&emsp;*`else-line`* *`text`*

*`else-line`*:\
&emsp;**`#else`**

*`endif-line`*:\
&emsp;**`#endif`**

*`digit-sequence`*:\
&emsp;*`digit`*\
&emsp;*`digit-sequence`* *`digit`*

*`digit`* ：以下之一\
&emsp;**`0` `1` `2` `3` `4` `5` `6` `7` `8` `9`**

*`token-string`*:\
&emsp;字符串 *`token`*

*`token`*:\
&emsp;*`keyword`*\
&emsp;*`identifier`*\
&emsp;*`constant`*\
&emsp;*`operator`*\
&emsp;*`punctuator`*

*`filename`*:\
&emsp;合法操作系统文件名

*`path-spec`*:\
&emsp;合法文件路径

*`text`*:\
&emsp;文本的任何序列

> [!NOTE]
> 以下非终止符在 *c + + 语言参考*：、、、、和的 "[词法约定](../cpp/lexical-conventions.md)" 部分中展开 *`constant`* *`constant-expression`* *`identifier`* *`keyword`* *`operator`* *`punctuator`* 。

## <a name="see-also"></a>另请参阅

[C/C++ 预处理器参考](../preprocessor/c-cpp-preprocessor-reference.md)
