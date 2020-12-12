---
description: '了解详细信息：/doc (处理文档注释)  (C/c + +) '
title: /doc（处理文档注释）(C/C++)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- /doc
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
helpviewer_keywords:
- /doc compiler option [C++]
- comments, C++ code
- XML documentation, comments in source files
- -doc compiler option [C++]
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
ms.openlocfilehash: ed811edff544c4b5b28baa67ed216fa09ea51092
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192871"
---
# <a name="doc-process-documentation-comments-cc"></a>/doc（处理文档注释）(C/C++)

导致编译器处理源代码文件中的文档注释，并为每个包含文档注释的源代码文件创建一个 .xdc 文件。

## <a name="syntax"></a>语法

> **/doc**[*名称*]

## <a name="arguments"></a>参数

*name*<br/>
编译器将创建的 .xdc 文件的名称。 仅在编译中传递一个 .cpp 文件时有效。

## <a name="remarks"></a>备注

.Xdc 文件使用 xdcmake.exe 处理到 .xml 文件中。 有关详细信息，请参阅 [XDCMake Reference](xdcmake-reference.md)。

您可以将文档注释添加到源代码文件中。 有关详细信息，请参阅 [建议的文档注释标记](recommended-tags-for-documentation-comments-visual-cpp.md)。

若要将生成的 .xml 文件与 IntelliSense 一起使用，请使 .xml 文件的文件名与你想要支持的程序集相同，并使 .xml 文件与程序集位于同一目录中。 在 Visual Studio 项目中引用程序集时，还会找到 .xml 文件。 有关详细信息，请参阅 [使用 IntelliSense](/visualstudio/ide/using-intellisense) 和 [提供 XML 代码注释](/visualstudio/ide/supplying-xml-code-comments)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **输出文件**" 属性页。

1. 修改 " **生成 XML 文档文件** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
