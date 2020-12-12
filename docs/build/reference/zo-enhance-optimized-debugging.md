---
description: '了解详细信息：/Zo (增强优化调试) '
title: /Zo（增强优化调试）
ms.date: 11/04/2016
f1_keywords:
- -Zo
- /Zo
helpviewer_keywords:
- Zo compiler option [C++]
- /Zo compiler option [C++]
- -Zo compiler option [C++]
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
ms.openlocfilehash: b2d5fb37205a6cf58492d7e6bc9080867ebacf54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224343"
---
# <a name="zo-enhance-optimized-debugging"></a>/Zo（增强优化调试）

在非调试生成中为优化代码生成增强调试信息。

## <a name="syntax"></a>语法

```cpp
/Zo[-]
```

## <a name="remarks"></a>备注

**/Zo** 编译器开关为优化代码生成增强的调试信息。 优化可能为本地变量、代码重新排序、向量化循环和内联函数调用使用寄存器。 这些优化可能会掩盖的源代码和编译的对象代码之间的关系。 **/Zo** 开关告诉编译器为本地变量和内联函数生成其他调试信息。 当你在 Visual Studio 调试器中逐句通过优化代码时，可以使用它来查看 "自动 **"、"****局部变量**" 和 "**监视**" 窗口中的变量。 它还启用堆栈跟踪以在 WinDBG 调试器中显示内联的函数。 禁用优化 ([/od](od-disable-debug.md)) 不需要在指定 **/Zo** 时生成的其他调试信息的调试版本。 使用 **/Zo** 开关调试启用了优化的版本配置。 有关优化开关的详细信息，请参阅 [/O 选项 (优化代码) ](o-options-optimize-code.md)。 使用 **/zi** 或 **/Z7** 指定调试信息时，Visual Studio 中默认情况下启用 **/Zo** 选项。 指定 **/Zo-** 以显式禁用此编译器选项。

**/Zo** 开关从 Visual Studio 2013 Update 3 开始提供，并替换之前未记录的 **/d2Zi +** 开关。

### <a name="to-set-the-zo-compiler-option-in-visual-studio"></a>在 Visual Studio 中设置 /Zo 编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 " **配置属性**" 和 " **c/c + +** " 文件夹。

1. 选择 " **命令行** " 属性页。

1. 修改 " **附加选项** " 属性以包含 `/Zo` ，然后选择 **"确定"**。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[/O 选项 (优化代码) ](o-options-optimize-code.md)<br/>
[/Z7、/Zi、/ZI (调试信息格式) ](z7-zi-zi-debug-information-format.md)<br/>
[编辑并继续](/visualstudio/debugger/edit-and-continue)
