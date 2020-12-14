---
description: '了解有关以下内容的详细信息：/P (预处理到文件) '
title: /P（预处理到文件）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFile
- /p
- VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile
helpviewer_keywords:
- /P compiler option [C++]
- -P compiler option [C++]
- P compiler option [C++]
- output files, preprocessor
- preprocessing output files
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
ms.openlocfilehash: 20bca03694c866baa0575445271fc4f587268096
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226189"
---
# <a name="p-preprocess-to-a-file"></a>/P（预处理到文件）

预处理 C 和 c + + 源文件，并将预处理的输出写入文件。

## <a name="syntax"></a>语法

```
/P
```

## <a name="remarks"></a>备注

该文件具有与源文件相同的基名称和扩展名。 在此过程中，将执行所有预处理器指令，执行宏展开，并删除注释。 若要在预处理输出中保留注释，请使用 [/c (在预处理期间保留注释)](c-preserve-comments-during-preprocessing.md) 选项连同 **/p** 一起使用。

**/P** 将 `#line` 指令添加到输出，每个包含的文件的开头和结尾，以及条件编译的预处理器指令删除的行。 这些指令对预处理文件的行进行重新编号。 因此，在后续的处理阶段生成的错误将引用原始源文件的行号，而不是预处理后的文件中的行的行号。 若要禁止生成 `#line` 指令，请使用 [/EP (预处理到 Stdout，而不 #line 指令)](ep-preprocess-to-stdout-without-hash-line-directives.md) 和 **/p**。

**/P** 选项取消编译。 即使使用 [/fo (对象文件名) ](fo-object-file-name.md)，它也不会生成 .obj 文件。 您必须重新提交预处理后的文件以进行编译。 **/P** 还禁止显示 **/FA**、 **/FA** 和 **/Fm** 选项中的输出文件。 有关详细信息，请参阅 [/FA、/FA (列出文件) ](fa-fa-listing-file.md) 和 [/Fm (名称映射文件) ](fm-name-mapfile.md)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 单击 " **预处理器** " 属性页。

1. 修改 " **生成预处理的文件** " 属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>。

## <a name="example"></a>示例

以下命令行预处理 `ADD.C` 、保留注释、添加 `#line` 指令并将结果写入文件 `ADD.I` ：

```
CL /P /C ADD.C
```

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)<br/>
[/Fi (预处理输出文件名) ](fi-preprocess-output-file-name.md)
