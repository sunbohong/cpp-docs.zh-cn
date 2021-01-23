---
description: 详细了解 pragma Microsoft c/c + + 中的 execution_character_set 指令
title: execution_character_set pragma
ms.date: 01/22/2021
f1_keywords:
- execution_character_set
- vc-pragma.execution_character_set
helpviewer_keywords:
- pragma, execution_character_set
- execution_character_set pragma
no-loc:
- pragma
ms.openlocfilehash: cc768aa0d35fffc9c387b31870adf47f35073f35
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712851"
---
# <a name="execution_character_set-no-locpragma"></a>`execution_character_set` pragma

指定用于字符串和字符文本的执行字符集。 用前缀标记的文本不需要此指令 `u8` 。

## <a name="syntax"></a>语法

> **`#pragma execution_character_set(`** "*target*" **`)`**

### <a name="parameters"></a>Parameters

*靶*\
指定目标执行字符集。 目前仅支持 "utf-8" 目标执行集。

## <a name="remarks"></a>注解

从 Visual Studio 2015 Update 2 开始，此编译器指令已过时。 建议将 **`/execution-charset:utf-8`** 或 **`/utf-8`** 编译器选项与在 `u8` 包含扩展字符的窄字符和字符串文本上使用前缀一起使用。 有关前缀的详细信息 `u8` ，请参阅 [字符串和字符文本](../cpp/string-and-character-literals-cpp.md)。 有关编译器选项的详细信息，请参阅[ `/execution-charset` (set 执行字符集) ](../build/reference/execution-charset-set-execution-character-set.md)和[ `/utf-8` (将源和可执行字符集设置为 utf-8) ](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)。

`#pragma execution_character_set("utf-8")`指令指示编译器将源代码中的窄字符和窄字符串文本编码为可执行文件中的 utf-8。 此输出编码独立于所使用的源文件编码。

默认情况下，编译器使用当前代码页作为执行字符集，对窄字符和窄字符串进行编码。 这意味着，在当前代码页范围外的 Unicode 或 DBCS 字符将转换为输出中的默认替换字符。 Unicode 和 DBCS 字符将被截断为低序位字节，这几乎不是您想要的。 您可以通过使用前缀为源文件中的文本指定 UTF-8 编码 `u8` 。 编译器将这些 UTF-8 编码的字符串传递给未更改的输出。 使用 u8 作为前缀的窄字符文本必须在一个字节内容纳，否则在输出时将被截断。

默认情况下，Visual Studio 使用当前代码页作为源字符集，用于解释输出的源代码。 当在中读取文件时，Visual Studio 将根据当前代码页对其进行解释，除非设置了文件代码页，否则，除非在文件开头检测到 (BOM) 或 UTF-16 字符，否则 Visual Studio 会将其解释为。 在某些版本的 Windows 中，不能将 UTF-8 设置为当前代码页。 当自动检测在这些版本中查找编码为 UTF-8 的源文件时，Visual Studio 会假设它们使用当前代码页进行编码。 源文件中的字符超出指定的或自动检测到的代码页的范围，可能导致编译器警告和错误。

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)\
[`/execution-charset` (设置执行字符集) ](../build/reference/execution-charset-set-execution-character-set.md)\
[`/utf-8` (将源和可执行字符集设置为 UTF-8) ](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)
