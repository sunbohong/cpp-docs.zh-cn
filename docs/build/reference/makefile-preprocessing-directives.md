---
description: 了解有关：生成文件预处理指令的详细信息
title: 生成文件预处理指令
ms.date: 08/11/2019
f1_keywords:
- '!UNDEF'
- '!INCLUDE'
- '!IFNDEF'
- '!MESSAGE'
helpviewer_keywords:
- ERROR directive
- '!MESSAGE directive'
- IF directive
- '!UNDEF directive'
- IFDEF directive
- '!ELSEIF directive'
- '!IFDEF directive'
- '!IF directive'
- UNDEF directive
- '!CMDSWITCHES directive'
- ENDIF directive
- directives, makefile preprocessing
- INCLUDE directive
- IFNDEF directive
- preprocessing directives, makefiles
- '!IFNDEF directive'
- ELSEIFNDEF directive
- NMAKE program, expressions
- ELSEIF directive
- '!ERROR directive'
- '!ENDIF directive'
- MESSAGE directive
- '!INCLUDE directive'
- '!ELSEIFNDEF directive'
- CMDSWITCHES directive
- '!ELSEIFDEF directive'
- '!ELSE directive'
- NMAKE program, preprocessor directives
- makefiles, preprocessing directives
- ELSE directive
- ELSEIFDEF directive
ms.assetid: bcedeccb-d981-469d-b9e8-ab5d097fd8c2
ms.openlocfilehash: 7c394e3547044be661fea5a8ec86f05a3b93e967
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138064"
---
# <a name="makefile-preprocessing-directives"></a>生成文件预处理指令

预处理指令不区分大小写。 初始惊叹号 (！ ) 必须出现在行的开头。 在感叹号后，对于缩进，零个或多个空格或制表符可以出现。

- `!CMDSWITCHES` { `+` &#124; `-` }*选项* .。。

   打开或关闭每个 *选项* 。 空格或制表符必须出现在 `+` or `-` 运算符之前; 运算符和 [选项字母](running-nmake.md#nmake-options)之间不能出现空格或制表符。 字母不区分大小写，但未指定斜线 (`/`) 。 若要打开某些选项并关闭其他选项，请使用的单独规范 `!CMDSWITCHES` 。

   只能在生成文件中使用/D、/I、/N 和/S。 在 Tools.ini 中，除/F、/HELP、/NOLOGO、/X 和/？之外的所有选项都是允许的。 在说明块中指定的更改在下一个描述块之前不会生效。 此指令更新 **MAKEFLAGS**;如果指定了 **MAKEFLAGS** ，则在递归期间会继承更改。

- `!ERROR` *文本*

   如果使用 () 命令修饰符，则显示错误 U1050 中的 *文本* ，然后停止 NMAKE，即使使用/K、/i、、 `.IGNORE` `!CMDSWITCHES` 或短划线 `-` 。 忽略 *文本* 之前的空格或制表符。

- `!MESSAGE` *文本*

   将 *文本* 显示到标准输出。 忽略 *文本* 之前的空格或制表符。

- `!INCLUDE` [ `<` ] *文件名* [ `>` ]

   将 *filename* 作为生成文件读取，然后继续当前的生成文件。 NMAKE 首先在指定的目录或当前目录中搜索 filename，然后以递归方式在任何父生成文件的目录中搜索 *文件名* ，然后，如果 *filename* 由尖括号括起来，则 `< >` 在由 **include** 宏指定的目录中 () ，最初设置为 include 环境变量。 向 `.SUFFIXES` 递归生成的传递设置、 `.PRECIOUS` 和推理规则非常有用。

- `!IF`*constant_expression*

   `!IF` `!ELSE` `!ENDIF` 如果 *constant_expression* 的计算结果为非零值，则处理和下一个 or 之间的语句。

- `!IFDEF` *macroname*

   在定义了 `!IFDEF` 和下一个之间 `!ELSE` 或 `!ENDIF` 如果定义了 *macroname* 。 空宏被视为已定义。

- `!IFNDEF` *macroname*

   在 `!IFNDEF` 和下一个之间处理语句， `!ELSE` `!ENDIF` 如果未定义 *macroname* ，则为。

- `!ELSE` [ `IF` *constant_expression* &#124; `IFDEF` *macroname* &#124; `IFNDEF` *macroname*]

   `!ELSE` `!ENDIF` 如果上一个 `!IF` 、 `!IFDEF` 或 `!IFNDEF` 语句的计算结果为零，则在和下一个语句之间进行处理。 可选关键字可进一步控制预处理。

- `!ELSEIF`

   `!ELSE IF` 的同义词。

- `!ELSEIFDEF`

   `!ELSE IFDEF` 的同义词。

- `!ELSEIFNDEF`

   `!ELSE IFNDEF` 的同义词。

- `!ENDIF`

   标记 `!IF` 、或块的结尾 `!IFDEF` `!IFNDEF` 。 位于同一行后面的任何文本 `!ENDIF` 都将被忽略。

- `!UNDEF` *macroname*

   取消 *macroname*。

## <a name="see-also"></a>请参阅

- [生成文件预处理](makefile-preprocessing.md)
