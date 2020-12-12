---
description: '了解详细信息： `/Fi` (预处理输出文件名) '
title: /Fi（预处理输出文件名）
ms.date: 08/12/2020
f1_keywords:
- /Fi
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
ms.openlocfilehash: c598730b19b843aa312df71d745ed363d082cc43
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192221"
---
# <a name="fi-preprocess-output-file-name"></a>`/Fi` (预处理输出文件名) 

指定[ `/P` (预处理到文件) ](p-preprocess-to-a-file.md)编译器选项写入预处理输出的输出文件的名称。

## <a name="syntax"></a>语法

> **`/Fi`**_`pathname`_

### <a name="parameters"></a>parameters

*`pathname`*\
编译器选项生成的输出文件的相对或绝对路径和文件名 **`/P`** 。 或， *`.i`* 当指定多个输入文件时，输出文件的目录路径。 不要在选项和之间加空格 **`/Fi`** *`pathname`* 。

## <a name="remarks"></a>备注

结合使用 **`/Fi`** 编译器选项和 **`/P`** 编译器选项。 如果 **`/P`** 未指定，则 **`/Fi`** 会导致命令行警告 D9007。

如果仅指定目录路径 (以反斜杠) 为参数结尾的路径 **`\`** *`pathname`* ，则源文件的基名称将用作预处理输出文件的基名称。 *`pathname`* 参数不需要特定的文件扩展名。 但是，如果不指定文件扩展名，则使用扩展名 ". i"。

### <a name="example"></a>示例

以下命令行预处理 *`PROGRAM.cpp`* 、保留注释、添加 [`#line`](../../preprocessor/hash-line-directive-c-cpp.md) 指令，并将结果写入 *`MYPROCESS.i`* 文件：

```cmd
CL /P /FiMYPROCESS.I PROGRAM.CPP
```

此命令行 *`main.cpp`* *`helper.cpp`* *`main.i`* *`helper.i`* 在名为的子目录中预处理和 into *`preprocessed`* ：

```cmd
CL /P /Fi".\\preprocessed\\" main.cpp helper.cpp
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开源文件或项目的 " **属性页** " 对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **预处理器**" 属性页。

1. 将 " **预处理到文件** " 属性设置为 **"是"**。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. **`/Fi`** *`pathname`* 在 "**附加选项**" 框中输入编译器选项。 为项目设置此属性时，只指定目录路径，而不指定文件名。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[`/P` (预处理到文件) ](p-preprocess-to-a-file.md)<br/>
[指定路径名](specifying-the-pathname.md)
