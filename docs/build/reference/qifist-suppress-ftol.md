---
description: '了解详细信息：/QIfist (取消 _ftol) '
title: /QIfist（取消 _ftol）
ms.date: 11/04/2016
f1_keywords:
- /qifist
helpviewer_keywords:
- QIfist compiler option [C++]
- -QIfist compiler option [C++]
- /QIfist compiler option [C++]
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
ms.openlocfilehash: 79e9242d66b532f558307d05b222b2fd8cfd43ab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225643"
---
# <a name="qifist-suppress-_ftol"></a>/QIfist（取消 _ftol）

已弃用。 当需要从浮点型转换为整型时，取消调用 Helper 函数 `_ftol` 。

## <a name="syntax"></a>语法

```
/QIfist
```

## <a name="remarks"></a>备注

> [!NOTE]
> **/QIfist** 仅在面向 x86 的编译器中可用;此编译器选项在面向 x64 用于的编译器中不可用。

除了从浮点类型转换为整型外， `_ftol` 函数还通过设置控制字的第10和第11个来确保 (FPU)  () 的浮点单元的舍入模式。 这可以保证从浮点类型转换为整型类型的操作如 ANSI C 标准 (会丢弃) 的小数部分。 当使用 **/QIfist** 时，此保证不再适用。 舍入模式将是 Intel 参考手册中所述的四种模式之一：

- 如果等距) ，则舍入到最接近的 (偶数

- 向负无穷舍入

- 向正无穷舍入

- 向零舍入

您可以使用 [_control87、_controlfp \_ _control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) C Run-Time 函数修改 FPU 的舍入行为。 FPU 的默认舍入模式为 "舍入到最接近的"。 使用 **/QIfist** 可以提高应用程序的性能，但不会带来风险。 在依赖于在生产环境中用 **/QIfist** 生成的代码之前，应全面测试代码中对舍入模式敏感的部分。

[/arch (x86)](arch-x86.md) 和 **/QIfist** 不能用于同一编译单位。

> [!NOTE]
> 默认情况下， **/QIfist** 不会生效，因为舍入点还会影响每个计算) 后的浮点舍入点舍入 (。因此，当你将 C 样式 (的标志方向设置为) 舍入时，浮点计算可能会不同。 如果代码依赖于截断浮点数的小数部分的预期行为，则不应使用 **/QIfist** 。 如果你不确定，请不要使用 **/QIfist**。

从 Visual Studio 2005 开始，已弃用 **/QIfist** 选项。 编译器已在 float 到 int 转换速度方面做了重大改进。 有关弃用的编译器选项的列表，请参阅 [按类别列出的编译器选项](compiler-options-listed-by-category.md)中的不 **推荐使用和已删除编译器选项**。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 点击“命令行”  属性页。

1. 在 **“附加选项”** 框中键入编译器选项。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[/Q 选项 (低级别操作) ](q-options-low-level-operations.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
