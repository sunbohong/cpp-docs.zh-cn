---
description: '了解更多相关信息：/EP (预处理到 stdout，无需 #line 指令) '
title: '/EP（不使用 #line 指令预处理到 stdout）'
ms.date: 11/04/2016
f1_keywords:
- /ep
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFileNoLines
helpviewer_keywords:
- copy preprocessor output to stdout
- preprocessor output, copy to stdout
- -EP compiler option [C++]
- EP compiler option [C++]
- /EP compiler option [C++]
ms.assetid: 6ec411ae-e33d-4ef5-956e-0054635eabea
ms.openlocfilehash: cbd36cd6bdafe315a7a6ef01b46857725033bd69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200996"
---
# <a name="ep-preprocess-to-stdout-without-line-directives"></a>/EP（不使用 #line 指令预处理到 stdout）

预处理 C 和 c + + 源文件，并将预处理过的文件复制到标准输出设备。

## <a name="syntax"></a>语法

```
/EP
```

## <a name="remarks"></a>备注

在此过程中，将执行所有预处理器指令，执行宏展开，并删除注释。 若要在预处理后的输出中保留注释，请使用 [/c (在预处理期间保留注释)](c-preserve-comments-during-preprocessing.md) 选项与 **/EP**。

**/EP** 选项取消编译。 您必须重新提交预处理后的文件以进行编译。 **/EP** 还会禁止显示 **/FA**、 **/FA** 和 **/Fm** 选项中的输出文件。 有关详细信息，请参阅 [/FA、/FA (列出文件) ](fa-fa-listing-file.md) 和 [/Fm (名称映射文件) ](fm-name-mapfile.md)。

在处理的后续阶段中生成的错误引用预处理文件的行号，而不是原始源文件的行号。 如果希望行号引用原始源文件，请改用 [/e (预处理为 stdout) ](e-preprocess-to-stdout.md) 。 **/E** 选项将 `#line` 指令添加到输出以实现此目的。

若要使用指令将预处理输出发送 `#line` 到文件，请改用 [/P (预处理到文件) ](p-preprocess-to-a-file.md) 选项。

若要使用指令将预处理输出发送到 stdout， `#line` 请同时使用 **/P** 和 **/EP** 。

不能将预编译标头与 **/EP** 选项一起使用。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 单击 " **预处理器** " 属性页。

1. 修改 " **生成预处理的文件** " 属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>。

## <a name="example"></a>示例

以下命令行预处理文件 `ADD.C` ，保留注释，并显示标准输出设备上的结果：

```
CL /EP /C ADD.C
```

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
