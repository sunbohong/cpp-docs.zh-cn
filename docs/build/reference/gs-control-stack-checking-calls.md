---
description: '了解详细信息：/Gs (控制堆栈检查调用) '
title: /Gs（控制堆栈检查调用）
ms.date: 10/25/2018
f1_keywords:
- /GS
helpviewer_keywords:
- disabling stack probes
- GS compiler option [C++]
- /GS compiler option [C++]
- stack, stack probes
- stack probes
- -GS compiler option [C++]
- stack checking calls
ms.assetid: 40daed7c-f942-4085-b872-01e12b37729e
ms.openlocfilehash: 128a5ad4dbcba15dfc5b76313b8576ce1448ec68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200152"
---
# <a name="gs-control-stack-checking-calls"></a>/Gs（控制堆栈检查调用）

控制堆栈探测的阈值。

## <a name="syntax"></a>语法

> **/Gs**[*大小*]

## <a name="arguments"></a>参数

*大小*<br/>
（可选）在启动堆栈探测之前局部变量可以占用的字节数。 **/Gs** 和 *size* 之间不允许有空格。

## <a name="remarks"></a>备注

*堆栈探测* 是编译器在函数调用开始时插入的代码序列。 堆栈探测启动时，它在内存中良性延伸存储函数的局部变量所需的空间量。 如果需要，在其余函数运行之前，这会使操作系统在其他堆栈内存中以透明方式分页。

默认情况下，当函数需要的堆栈空间多于一页时，编译器将生成启动堆栈探测的代码。 这等效于 x86、x64、ARM 和 ARM64 平台的 **/Gs4096** 编译器选项。 此值使应用程序和 Windows 内存管理器可以动态增加运行时提交给程序堆栈的内存量。

> [!NOTE]
> **/Gs4096** 的默认值允许 Windows 应用程序的程序堆栈在运行时正确增长。 我们建议，除非有确切的理由，否则请不要更改默认值。

某些程序（如虚拟设备驱动程序）并不需要这种默认堆栈增长机制。 在这种情况下，不需要堆栈探测，并且可以通过将 *大小* 设置为大于任何函数对本地变量存储所需的值来阻止编译器生成它们。

**/Gs0** 为需要局部变量存储的每个函数调用启动堆栈探测。 这可对性能产生负面影响。

对于 x64 目标，如果指定的 **/gs** 选项没有 *大小* 参数，则该选项与 **/Gs0** 相同。 如果 *size* 参数为1到9，则发出警告 D9014，其效果与指定 **/Gs0** 相同。

对于 x86、ARM 和 ARM64 目标，没有 *大小* 自变量的 **/Gs** 选项与 **/Gs4096** 相同。 如果 *size* 参数为1到9，则发出警告 D9014，其效果与指定 **/Gs4096** 相同。

对于所有目标，介于10和2147485647之间的 *大小* 参数设置指定值的阈值。 2147485648或更大的 *大小* 导致严重错误 C1049。

您可以使用 [check_stack](../../preprocessor/check-stack.md) 指令打开或关闭堆栈探测。 **/Gs** 和 `check_stack` 杂注对标准 C 库例程不起作用; 它们只影响你编译的函数。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. 在 **其他选项** 中输入 **/gs** 编译器选项和可选大小。 选择 **"确定" 或 "** **应用** " 保存更改。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
