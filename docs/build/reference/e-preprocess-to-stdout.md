---
description: '了解详细信息：/E (预处理为 stdout) '
title: /E（预处理到 stdout）
ms.date: 11/04/2016
f1_keywords:
- /e
helpviewer_keywords:
- -E compiler option [C++]
- /E compiler option [C++]
- preprocessor output, copy to stdout
- preprocessor output
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
ms.openlocfilehash: 9d6c9ea3a5fcf8e7ba06ede6e7e70d933b5c921a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192599"
---
# <a name="e-preprocess-to-stdout"></a>/E（预处理到 stdout）

预处理 C 和 c + + 源文件，并将预处理过的文件复制到标准输出设备。

## <a name="syntax"></a>语法

```
/E
```

## <a name="remarks"></a>备注

在此过程中，将执行所有预处理器指令，执行宏展开，并删除注释。 若要在预处理输出中保留注释，请在 [预处理) 编译器选项时使用/c (保留注释 ](c-preserve-comments-during-preprocessing.md) 。

**/E** 将 `#line` 指令添加到每个包含的文件的开头和结尾处以及由预处理器指令删除的行，以进行条件编译。 这些指令对预处理文件的行进行重新编号。 因此，在后续的处理阶段生成的错误将引用原始源文件的行号，而不是预处理后的文件中的行的行号。

**/E** 选项取消编译。 您必须重新提交预处理后的文件以进行编译。 **/E** 还禁止显示 **/FA**、 **/FA** 和 **/Fm** 选项中的输出文件。 有关详细信息，请参阅 [/FA、/FA (列出文件) ](fa-fa-listing-file.md) 和 [/Fm (名称映射文件) ](fm-name-mapfile.md)。

若要取消 `#line` 指令，请使用 [/EP (预处理为 stdout，而不 #line 指令) ](ep-preprocess-to-stdout-without-hash-line-directives.md) 选项。

若要将预处理输出发送到文件而不是发送到 `stdout` ，请改用 [/P (预处理到文件) ](p-preprocess-to-a-file.md) 选项。

若要取消 `#line` 指令并将预处理输出发送到文件，请同时使用 **/P** 和 **/EP** 。

不能将预编译标头与 **/e** 选项一起使用。

请注意，在向单独的文件进行预处理时，不会在标记后发出空格。 这可能导致非法程序或意外的副作用。 以下程序编译成功：

```
#define m(x) x
m(int)main( )
{
   return 0;
}
```

但是，如果用以下内容编译：

```
cl -E test.cpp > test2.cpp
```

`int main` 不正确的 `intmain` test2。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 点击“命令行”  属性页。

1. 在 " **附加选项**" 框中键入编译器选项。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>。

## <a name="example"></a>示例

以下命令行预处理 `ADD.C` 、保留注释、添加 `#line` 指令，并显示标准输出设备上的结果：

```
CL /E /C ADD.C
```

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
