---
description: '了解详细信息：/arch (ARM) '
title: /arch (ARM)
ms.date: 11/04/2016
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
ms.openlocfilehash: 885b624eb6a470d24d691641d0be63515ee76a49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179559"
---
# <a name="arch-arm"></a>/arch (ARM)

为 ARM 上的代码生成指定体系结构。 另请参阅 [/arch (x86) ](arch-x86.md) 和 [/arch (x64) ](arch-x64.md)。

## <a name="syntax"></a>语法

```
/arch:[ARMv7VE|VFPv4]
```

## <a name="arguments"></a>参数

**/arch： ARMv7VE**<br/>
允许使用 ARMv7VE 虚拟化扩展指令。

**/arch： VFPv4**<br/>
允许使用 ARM VFPv4 指令。 如果未指定此选项，则默认为 VFPv3。

## <a name="remarks"></a>备注

`_M_ARM_FP`ARM 的宏 (仅) 指示使用了哪个 **/arch** 编译器选项。 有关更多信息，请参见 [Predefined Macros](../../preprocessor/predefined-macros.md)。

使用 [/clr](clr-common-language-runtime-compilation.md) 进行编译时， **/arch** 不会影响托管函数的代码生成。 **/arch** 仅影响本机函数的代码生成。

### <a name="to-set-the-archarmv7ve-or-archvfpv4-compiler-option-in-visual-studio"></a>在 Visual Studio 中设置 /arch:ARMv7VE 或 /arch:VFPv4 编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 " **c/c + +** " 文件夹。

1. 选择 " **命令行** " 属性页。

1. 在 " **附加选项** " 框中，添加 `/arch:ARMv7VE` 或 `/arch:VFPv4` 。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>。

## <a name="see-also"></a>请参阅

[/arch (最小 CPU 体系结构) ](arch-minimum-cpu-architecture.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
