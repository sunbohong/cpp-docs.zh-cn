---
description: '了解详细信息：/FI (名称强制包含文件) '
title: /FI（命名强制包含文件）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.ForcedIncludes
- VC.Project.VCCLCompilerTool.ForcedIncludeFiles
- VC.Project.VCCLWCECompilerTool.ForcedIncludeFiles
helpviewer_keywords:
- FI compiler option [C++]
- -FI compiler option [C++]
- /FI compiler option [C++]
- preprocess header file compiler option [C++]
ms.assetid: 07e79577-8152-4df9-a64c-aae08c603397
ms.openlocfilehash: 614a06511df1b407adc39bb8ec567a9674ffb3cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200645"
---
# <a name="fi-name-forced-include-file"></a>/FI（命名强制包含文件）

使预处理器处理指定的标头文件。

## <a name="syntax"></a>语法

```
/FI[ ]pathname
```

## <a name="remarks"></a>备注

此选项的效果与在 `#include` 命令行上、CL 环境变量或命令文件中指定的每个源文件第一行的指令中指定带有双引号的文件的效果相同。 如果使用多个 **/fi** 选项，则按 CL 处理文件的顺序包含这些文件。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 单击 " **高级** " 属性页。

1. 修改 " **强制包含文件** " 属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>。

## <a name="see-also"></a>请参阅

[Output-File (/F) 选项](output-file-f-options.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)<br/>
[指定路径名](specifying-the-pathname.md)
