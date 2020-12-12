---
description: '了解详细信息：/AI (指定元数据目录) '
title: /AI（指定元数据目录）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.AdditionalUsingDirectories
- VC.Project.VCNMakeTool.AssemblySearchPath
- /AI
- VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories
helpviewer_keywords:
- /AI compiler option [C++]
- AI compiler option [C++]
- -AI compiler option [C++]
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
ms.openlocfilehash: e30711b1da2d41204bf56520d56dd5101f3168b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179741"
---
# <a name="ai-specify-metadata-directories"></a>/AI（指定元数据目录）

指定在解析传递给 `#using` 指令的文件引用时编译器将搜索的目录。

## <a name="syntax"></a>语法

> **/AI**_目录_

## <a name="arguments"></a>参数

*文件夹*<br/>
编译器要搜索的目录或路径。

## <a name="remarks"></a>备注

只有一个目录可以传递到 **/AI** 调用。 为希望编译器搜索的每个路径指定一个 **/AI** 选项。 例如，若要将 C:\Project\Meta 和 C:\Common\Meta 添加到指令的编译器搜索路径 `#using` 中，请将添加 `/AI"C:\Project\Meta" /AI"C:\Common\Meta"` 到编译器命令行，或将每个目录添加到 Visual Studio 中的 " **其他 #using 目录** " 属性。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择“配置属性” > “C/C++” > “常规”属性页    。

1. 修改 " **其他 #using 目录** " 属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)<br/>
[#using 指令](../../preprocessor/hash-using-directive-cpp.md)
