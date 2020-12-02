---
title: /FA、/Fa（列出文件）
description: Microsoft c + +/FA and/Fa (列出文件) 编译器选项的参考指南。
ms.date: 11/21/2020
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AssemblerListingLocation
- VC.Project.VCCLCompilerTool.ConfigureASMListing
- VC.Project.VCCLWCECompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.AssemblerListingLocation
- /fa
- VC.Project.VCCLCompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing
helpviewer_keywords:
- FA compiler option [C++]
- /FA compiler option [C++]
- -FA compiler option [C++]
- listing file type
- assembly-only listing
ms.openlocfilehash: 7e8e39fea55bb69eaa0ae914eeabcafef4ac7849
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440230"
---
# <a name="fa-fa-listing-file"></a>`/FA`， `/Fa` (列出文件) 

创建包含组装器代码的列表文件。

## <a name="syntax"></a>语法

> **`/FA`**[**`c`**\][**`s`**\][**`u`**]\
> **`/Fa`**_路径名_

## <a name="remarks"></a>备注

**`/FA`** 编译器选项为编译中的每个翻译单元生成汇编程序列表文件，这通常对应于 c 或 c + + 源文件。 默认情况下，仅在列表文件中包含汇编程序，其编码为 ANSI。 可选的 **`c`** 、 **`s`** 和 **`u`** 参数，用于 **`/FA`** 控制是否将计算机代码或源代码与组装器列表一起输出，以及列表是否被编码为 utf-8。

默认情况下，每个列表文件将获取与源文件相同的基名称，并且具有 *`.asm`* 扩展名。 当使用选项包含计算机代码时 **`c`** ，列表文件具有 *`.cod`* 扩展名。 你可以使用选项更改列表文件的名称和扩展名，以及在其中创建列表文件的目录 **`/Fa`** 。

### <a name="fa-arguments"></a>`/FA` 参数

内容
列表中仅包含汇编程序语言。

**`c`**\
可选。 将计算机代码包含在列表中。

**`s`**\
可选。 包含列表中的源代码。

**`u`**\
可选。 使用 UTF-8 格式对列表文件进行编码，并包含字节顺序标记。 默认情况下，该文件编码为 ANSI。 使用 **`u`** 可以创建在任何系统上正确显示的列表文件，如果使用 Unicode 源代码文件作为编译器的输入，则使用。

如果同时 **`s`** **`u`** 指定了和，并且如果源代码文件使用 utf-8 以外的 Unicode 编码，则文件中的代码行 *`.asm`* 可能无法正确显示。

### <a name="fa-argument"></a>`/Fa` 参数

内容
为编译中的每个源代码文件创建一个 " *源 .asm* " 文件。

*名字*\
编译器在当前目录中放置名为 *filename* 的列表文件。 此参数形式只有在编译单个源代码文件时才有效。

*filename 扩展名*\
编译器将在当前目录中放置一个名为 *filename. extension* 的列表文件。 此参数形式只有在编译单个源代码文件时才有效。

*文件夹*__\\__\
编译器会为编译中的每个源代码文件创建一个 *source_file .asm* 文件。 将其放在指定的 *目录* 中。 尾随反斜杠是必需的。 仅允许当前磁盘上的路径。

*目录* __\\__*filename*\
将名为 *filename* 的列表文件放在指定的 *目录* 中。 此参数形式只有在编译单个源代码文件时才有效。

*目录* __\\__*filename 扩展名*\
将名为 *filename* 的列表文件放在指定的 *目录* 中。 此参数形式只有在编译单个源代码文件时才有效。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **输出文件**" 属性页。

1. 修改 **汇编程序 Output** 属性，为汇编程序、计算机和源代码设置 **/FAc** 和 **/FAs** 选项。 修改 " **使用用于汇编程序的 Unicode 列表** " 属性，设置 **`/FAu`** ANSI 或 utf-8 输出的选项。 修改 **ASM 列表位置** 以设置 **`/Fa`** 用于列出文件名和位置的选项。

**为汇编程序列表** 属性设置 **汇编程序输出** 和使用 Unicode 可能会导致 [命令行警告 D9025](../../error-messages/tool-errors/command-line-warning-d9025.md)。 若要在 IDE 中组合这些选项，请改用 "**命令行**" 属性页中的 "**其他选项**" 字段。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参见<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerListingLocation%2A>或 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerOutput%2A>。 若要指定 **/FAu**，请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> 。

## <a name="example"></a>示例

下面的命令行生成一个名为的组合源和计算机代码列表 *`HELLO.cod`* ：

```cmd
CL /FAcs HELLO.CPP
```

## <a name="see-also"></a>请参阅

[Output-File (/F) 选项](output-file-f-options.md)\
[MSVC 编译器选项](compiler-options.md)\
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)\
[指定路径名](specifying-the-pathname.md)
