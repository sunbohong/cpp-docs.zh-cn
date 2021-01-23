---
description: '了解详细信息：/I (其他包含目录) '
title: /I（附加包含目录）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories
- VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories
- /I
- VC.Project.VCNMakeTool.IncludeSearchPath
helpviewer_keywords:
- /I compiler option [C++]
- Additional Include Directories compiler option
- I compiler option [C++]
- -I compiler option [C++]
- set include directories
- include directories, compiler option [C++]
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
ms.openlocfilehash: 36da00f9a6d5a55e60efd60a941ac3a9b3bfa4ec
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712786"
---
# <a name="i-additional-include-directories"></a>`/I` (其他包含目录) 

将目录添加到搜索包含文件的目录列表。

## <a name="syntax"></a>语法

> **`/I`***目录*

### <a name="arguments"></a>参数

*文件夹*\
要添加到搜索包含文件的目录列表中的目录。 `/I`和 *目录* 之间的空格是可选的。 包含空格的目录必须用双引号引起来。 目录可以是绝对路径或相对路径。

## <a name="remarks"></a>注解

若要添加多个目录，请使用此选项多次。 仅在找到指定的包含文件之前搜索目录。

可以在与 ([ `/X` (忽略标准包含路径) ](x-ignore-standard-include-paths.md)) 选项相同的命令行上使用此选项。

例如，可以在双引号 (或本地优先) 形式中指定[ `#include` 指令](../../preprocessor/hash-include-directive-c-cpp.md) `#include "local.h"` 。 或者，可以在尖括号中指定 (或包含路径优先) 形式，例如 `#include <iostream>` 。

编译器会按以下顺序搜索目录：

1. 如果 **`#include`** 指令是使用双引号格式指定的，则它首先搜索本地目录。 搜索在包含指令的文件所在的目录中开始 **`#include`** 。 如果找不到该文件，它将在当前打开的包含文件的目录中的下一项搜索，其顺序与它们的打开顺序相反。 搜索从父包含文件的目录中开始进行，然后继续向上到任何祖父包含文件的目录。

1. 如果 **`#include`** 指令是以尖括号形式指定的，或者如果本地目录搜索失败，则它会按照 **`/I`** 命令行中指定的顺序搜索使用选项指定的目录。

1. 在环境变量中指定的目录 **`INCLUDE`** 。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择“配置属性” > “C/C++” > “常规”属性页    。

1. 修改 " **附加包含目录** " 属性。 您可以在此属性中一次指定多个目录。 目录必须由分号分隔 (**`;`**) 。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>。

## <a name="example"></a>示例

以下命令将按以下顺序查找所请求的包含文件 *`main.c`* ：第一个，如果使用双引号指定，则搜索本地文件。 接下来，在目录中，然后在目录中继续搜索， *`\include`* *`\my\include`* 最后在分配给环境变量的目录中以 **`INCLUDE`** 从左到右的顺序继续搜索。

```cmd
CL /I \include /I\my\include main.c
```

## <a name="see-also"></a>另请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
