---
description: 了解详细信息： CL 环境变量
title: CL 环境变量
ms.date: 06/06/2019
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
ms.openlocfilehash: 1be95d2c2eddd204846fbcdc8675f28d71c25c0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179169"
---
# <a name="cl-environment-variables"></a>CL 环境变量

CL 工具使用以下环境变量:

- CL 和 \_ CL_ （如果已定义）。 CL 工具将 CL 环境变量中定义的选项和参数预先添加到命令行参数，并在处理前追加 CL_ 中定义的选项和参数 \_ 。

- 包括，其中必须指向 Visual Studio 安装的 \include 子目录。

- LIBPATH，它指定要在其中搜索 [#using](../../preprocessor/hash-using-directive-cpp.md)引用的元数据文件的目录。 有关 LIBPATH 的详细信息，请参阅 [#using](../../preprocessor/hash-using-directive-cpp.md)。

您可以 \_ 使用以下语法设置 CL 或 CL_ 环境变量：

> 设置 CL = [[*选项*] .。。[*文件*] ...][/link *链接-opt* ...]\
> 设置 \_ CL \_ = [[*选项*] .。。[*文件*] ...][/link *链接-opt* ...]

有关 CL 和 CL_ 环境变量的参数的详细信息 \_ ，请参阅 [MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)。

您可以使用这些环境变量来定义最常使用的文件和选项。 然后，使用命令行为特定用途提供更多的文件和选项。 CL 和 \_ CL_ 环境变量限制为1024个字符 () 的命令行输入限制。

不能使用 [/d](d-preprocessor-definitions.md) 选项来定义使用等号 () 的符号 **=** 。 相反，可以使用数字符号 (**#**) 来表示等号。 通过这种方式，可以使用 CL 或 \_ CL_ 环境变量来定义具有显式值的预处理器常量（例如， `/DDEBUG#1` 定义） `DEBUG=1` 。

有关相关信息，请参阅 [设置环境变量](../setting-the-path-and-environment-variables-for-command-line-builds.md)。

## <a name="examples"></a>示例

以下命令是设置 CL 环境变量的示例：

> SET CL =/Zp2/Ox/I\INCLUDE\MYINCLS \LIB\BINMODE。OBJ

如果设置了 CL 环境变量，则在 `CL INPUT.C` 命令行中输入时，有效的命令将变为：

> CL/Zp2/Ox/I\INCLUDE\MYINCLS \LIB\BINMODE。OBJ 输入。Ansi-c

下面的示例使普通 CL 命令编译源文件 FILE1.c 和 FILE2.c，然后链接对象文件 FILE1.obj、FILE2.obj 和 FILE3.obj：

> 设置 CL = FILE1。C FILE2。Ansi-c
> 将 \_ CL_ 设置为 FILE3。OBJ
> CL

这些环境变量对 CL 的调用与以下命令行具有相同的效果：

> CL FILE1。C FILE2。C FILE3。OBJ

## <a name="see-also"></a>请参阅

[设置编译器选项](compiler-command-line-syntax.md) \
[MSVC 编译器选项](compiler-options.md)
