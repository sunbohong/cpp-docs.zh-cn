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
ms.openlocfilehash: ad44abec28bbb87f91f449765a9ea2f30f2bffa8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191337"
---
# <a name="i-additional-include-directories"></a>/I（附加包含目录）

将目录添加到搜索包含文件的目录列表。

## <a name="syntax"></a>语法

> **/I**[]*目录*

### <a name="arguments"></a>参数

*文件夹*<br/>
要添加到搜索包含文件的目录列表中的目录。

## <a name="remarks"></a>备注

若要添加多个目录，请使用此选项多次。 仅在找到指定的包含文件之前搜索目录。

可以将此选项与 (/X 一起使用 [ (忽略标准包含路径) ](x-ignore-standard-include-paths.md)) 选项。

编译器会按以下顺序搜索目录：

1. 如果使用双引号形式的 [#include 指令](../../preprocessor/hash-include-directive-c-cpp.md) 指定，则它首先搜索本地目录。 搜索在包含 **#include** 语句的文件所在的目录中开始。 如果找不到该文件，它将在当前打开的包含文件的目录中搜索它们的打开顺序。 搜索从父包含文件的目录中开始进行，然后继续向上到任何祖父包含文件的目录。

1. 如果使用尖括号窗体中的 **#include** 指令指定，或者如果本地目录搜索失败，则它将使用 **/i** 选项搜索指定的目录，并以 CL 在命令行上遇到它们的顺序进行搜索。

1. 在 **INCLUDE** 环境变量中指定的目录。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择“配置属性” > “C/C++” > “常规”属性页    。

1. 修改 " **附加包含目录** " 属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>。

## <a name="example"></a>示例

以下命令将按以下顺序查找 MAIN 请求的包含文件：第一个，如果使用双引号指定，则搜索本地文件。 接下来，在 \INCLUDE 目录中继续搜索，然后在 \MY\INCLUDE 目录中搜索，最后在分配给 INCLUDE 环境变量的目录中。

```
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C
```

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
