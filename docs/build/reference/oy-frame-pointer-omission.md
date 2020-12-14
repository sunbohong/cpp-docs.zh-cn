---
description: '了解详细信息：/Oy (框架指针省略) '
title: /Oy（框架指针省略）
ms.date: 11/19/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.OmitFramePointers
- /oy
helpviewer_keywords:
- omit frame pointer
- Oy compiler option [C++]
- stack frame pointer compiler option [C++]
- -Oy compiler option [C++]
- frame pointer omission compiler option [C++]
- suppress frame pointer creation
- /Oy compiler option [C++]
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
ms.openlocfilehash: dc0f9272bce5ad36840eac9ccdfc7e2465f7e3c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226293"
---
# <a name="oy-frame-pointer-omission"></a>/Oy（框架指针省略）

禁止在调用堆栈上创建帧指针。

## <a name="syntax"></a>语法

> /Oy [-]

## <a name="remarks"></a>备注

此选项可以加快函数调用的速度，因为无需设置和移除任何框架指针。 它还会释放另一个寄存器来实现常规用途。

**/Oy** 启用框架指针省略和 **/Oy-** 禁用省略。 在 x64 编译器中， **/oy** 和 **/Oy-** 不可用。

如果你的代码需要基于帧的寻址，则可以在 **/ox** 选项后指定 **/Oy-** 选项，或使用带有 "**y**" 和 " **off** " 参数的 [optimize](../../preprocessor/optimize.md)来通过基于帧的寻址获得最大程度的优化。 编译器检测到大多数情况下，在这种情况下，需要基于帧的寻址 (例如，具有 `_alloca` 和 `setjmp` 函数以及结构化异常处理) 。

[/Ox (实现最](ox-full-optimization.md)大程度的优化) 和 [/O1、/O2 (最小化大小、最大化速度)](o1-o2-minimize-size-maximize-speed.md)选项意味着 **/oy**。 如果在 **/ox**、 **/O1** 或 **/O2** 选项后指定 **/Oy-** ，则将禁用 **/oy**，无论它是显式的还是隐式的。

使用 **/oy** 编译器选项可以更难地使用调试器，因为编译器会取消帧指针信息。 如果 ([/Z7、/zi、/zi](z7-zi-zi-debug-information-format.md)) 指定调试编译器选项，则建议在任何其他优化编译器选项后指定 **/Oy-** 选项。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **优化**" 属性页。

1. 修改 **省略帧指针** 属性。 此属性仅添加或删除 **/oy** 选项。 如果要添加 **/Oy-** 选项，请选择 " **命令行** " 属性页，然后修改 **其他选项**。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>。

## <a name="see-also"></a>请参阅

[/O 选项 (优化代码) ](o-options-optimize-code.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)<br/>
