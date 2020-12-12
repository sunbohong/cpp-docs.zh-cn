---
description: 详细了解：编译器 Command-Line 语法
title: MSVC 编译器 Command-Line 语法
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
ms.openlocfilehash: 91340aa543f0e79d3071b93921742b8147918b2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182211"
---
# <a name="compiler-command-line-syntax"></a>编译器命令行语法

CL 命令行使用以下语法：

```
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]
```

下表描述了 CL 命令的输入。

|条目|含义|
|-----------|-------------|
|*option*|一个或多个 [CL 选项](compiler-options.md)。 请注意，所有选项都适用于所有指定的源文件。 选项由正斜杠 (/) 或短划线 (-) 指定。 如果选项采用参数，则选项的说明会记录选项和参数之间是否允许有空格。 除了/HELP 选项外)  (选项名称不区分大小写。 有关详细信息，请参阅 [CL 选项的顺序](order-of-cl-options.md) 。|
|`file`|一个或多个源文件、.obj 文件或库的名称。 CL 编译源文件，并将 .obj 文件和库的名称传递到链接器。 有关详细信息，请参阅 [CL 文件名语法](cl-filename-syntax.md) 。|
|*lib*|一个或多个库名称。 CL 将这些名称传递到链接器。|
|*命令文件*|包含多个选项和文件名的文件。 有关详细信息，请参阅 [CL 命令文件](cl-command-files.md) 。|
|*链接-选择*|一个或多个 [MSVC 链接器选项](linker-options.md)。 CL 将这些选项传递到链接器。|

可以指定任意数量的选项、文件名和库名称，前提是命令行上的字符数不超过1024，这是操作系统所规定的限制。

有关 cl.exe 的返回值的信息，请参阅 [cl.exe的返回值 ](return-value-of-cl-exe.md) 。

> [!NOTE]
> 在将来的 Windows 版本中，不保证命令行输入限制为1024个字符。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)
