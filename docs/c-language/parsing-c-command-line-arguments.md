---
title: 分析 C 命令行自变量
description: 了解 Microsoft C 运行时启动代码如何解释命令行参数以创建 argv 和 argc 参数。
ms.date: 11/09/2020
helpviewer_keywords:
- quotation marks, command-line arguments
- double quotation marks
- double quote marks
- command line, parsing
- parsing, command-line arguments
- startup code, parsing command-line arguments
ms.assetid: ffce8037-2811-45c4-8db4-1ed787859c80
ms.openlocfilehash: 92921e91ee6bb37b2bf7b702a1b31ed045187b59
ms.sourcegitcommit: b38485bb3a9d479e0c5d64ffc3d841fa2c2b366f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441250"
---
# <a name="parsing-c-command-line-arguments"></a>分析 C 命令行自变量

**Microsoft 专用**

在解释操作系统命令行上给出的自变量时，Microsoft C 启动代码使用下列规则：

- 参数用空白分隔，空白可以是一个空格或制表符。

- 第一个参数 (`argv[0]`) 是经过专门处理的。 它表示程序名称。 因为它必须是有效的路径名，因此允许用双引号 (`"`) 括起来一些部分。 双引号不包含在 `argv[0]` 输出中。 用双引号括起来的部分可以防止将空格或制表符解释为参数的末尾。 此列表中的后续规则不适用。

- 无论其中是否包含空格，双引号括起来的字符串均被解释为单个参数。 带引号的字符串可以嵌入在自变量内。 插入点 (`^`) 未被识别为转义字符或者分隔符。 在带引号的字符串中，一对双引号被解释为单个转义的双引号。 如果在找到右双引号之前命令行结束，则到目前为止读取的所有字符都将输出为最后一个参数。

- 前面有反斜杠的双引号 (`\"`) 被解释为原义双引号 (`"`)。

- 反斜杠按其原义解释，除非它们紧位于双引号之前。

- 如果偶数个反斜杠后跟双引号，则每对反斜杠 (`\\`) 中有一个反斜杠 (`\`) 被置于 `argv` 数组中，而双引号 (`"`) 被解释为字符串分隔符。

- 如果奇数个反斜杠后跟双引号，则每对反斜杠 (`\\`) 中有一个反斜杠 (`\`) 被置于 `argv` 数组中。 双引号由剩余反斜杠解释为转义序列，导致原义双引号 (`"`) 被置于 `argv` 中。

此列表通过显示命令行参数的多个示例的传递到 `argv` 的解释结果来阐释上述规则。 在第二列、第三列和第四列中列出的输出来自于遵循列表的 ARGS.C 程序。

|命令行输入|argv[1]|argv[2]|argv[3]|
|-------------------------|---------------|---------------|---------------|
|`"a b c" d e`|`a b c`|`d`|`e`|
|`"ab\"c" "\\" d`|`ab"c`|`\`|`d`|
|`a\\\b d"e f"g h`|`a\\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|
|`a"b"" c d`|`ab" c d`|||

## <a name="example"></a>示例

### <a name="code"></a>代码

```c
// ARGS.C illustrates the following variables used for accessing
// command-line arguments and environment variables:
// argc  argv  envp
//

#include <stdio.h>

int main( int argc, // Number of strings in array argv
char *argv[],      // Array of command-line argument strings
char **envp )      // Array of environment variable strings
{
    int count;

    // Display each command-line argument.
    printf_s( "\nCommand-line arguments:\n" );
    for( count = 0; count < argc; count++ )
        printf_s( "  argv[%d]   %s\n", count, argv[count] );

    // Display each environment variable.
    printf_s( "\nEnvironment variables:\n" );
    while( *envp != NULL )
        printf_s( "  %s\n", *(envp++) );

    return;
}
```

## <a name="comments"></a>注释

此程序中输出的一个示例是：

```
Command-line arguments:
  argv[0]   C:\MSC\TEST.EXE

Environment variables:
  COMSPEC=C:\NT\SYSTEM32\CMD.EXE

  PATH=c:\nt;c:\binb;c:\binr;c:\nt\system32;c:\word;c:\help;c:\msc;c:\;
  PROMPT=[$p]
  TEMP=c:\tmp
  TMP=c:\tmp
  EDITORS=c:\binr
  WINDIR=c:\nt
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[main 函数和程序执行](../c-language/main-function-and-program-execution.md)
