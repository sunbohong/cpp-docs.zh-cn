---
description: 了解详细信息：/Qsafe_fp_loads
title: /Qsafe_fp_loads
ms.date: 01/24/2018
ms.openlocfilehash: e569b308d2da982c72775699ff2149daa45a8f2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225513"
---
# <a name="qsafe_fp_loads"></a>/Qsafe_fp_loads

要求对浮点值使用整数移动指令，并禁用特定浮点加载优化。

## <a name="syntax"></a>语法

> **/Qsafe_fp_loads**

## <a name="remarks"></a>备注

**/Qsafe_fp_loads** 仅在面向 x86 的编译器中可用;它在面向 x64 或 ARM 的编译器中不可用。

**/Qsafe_fp_loads** 强制编译器使用整数移动指令而不是浮点移动指令在内存和 MMX 寄存器之间移动数据。 多个控制路径中可加载的浮点值可能导致加载异常（例如 NaN 值）时，此选项还禁用这些值的寄存器加载优化。

[/Fp： except](fp-specify-floating-point-behavior.md)覆盖此选项。 **/Qsafe_fp_loads** 指定由 **/fp： except** 指定的一小部分编译器行为。

**/Qsafe_fp_loads** 与 [/clr](clr-common-language-runtime-compilation.md) 和 [/fp： fast](fp-specify-floating-point-behavior.md)不兼容。 有关浮点编译器选项的详细信息，请参阅 [/fp (指定 Floating-Point 行为) ](fp-specify-floating-point-behavior.md)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. 在 " **附加选项** " 框中输入编译器选项。 选择“确定”应用更改。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[/Q 选项 (低级别操作) ](q-options-low-level-operations.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
