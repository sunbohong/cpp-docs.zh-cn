---
description: '了解详细信息：/Gw (优化全局数据) '
title: /Gw（优化全局数据）
ms.date: 11/04/2016
f1_keywords:
- /Gw
helpviewer_keywords:
- /Gw compiler option [C++]
- -Gw compiler option [C++]
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
ms.openlocfilehash: 2f9a6b9452f09473e650a5453ad2600cc73f0c00
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200138"
---
# <a name="gw-optimize-global-data"></a>/Gw（优化全局数据）

在 COMDAT 节中打包全局数据以进行优化。

## <a name="syntax"></a>语法

```
/Gw[-]
```

## <a name="remarks"></a>备注

**/Gw** 选项使编译器将全局数据打包到各个 COMDAT 部分中。 默认情况下， **/Gw** 处于关闭状态，必须显式启用。 若要显式禁用它，请使用 **/Gw-**。 当同时启用 **/Gw** 和 [/gl](gl-whole-program-optimization.md) 时，链接器将使用全程序优化来比较多个对象文件中的 COMDAT 节，以便排除未引用的全局数据或合并相同的只读全局数据。 这样可以显著减小生成的二进制可执行文件的大小。

单独编译和链接时，可以使用 [/opt： REF](opt-optimizations.md) 链接器选项从可执行文件中排除使用 **/Gw** 选项编译的对象文件中的未引用全局数据。

你还可以结合使用 [/opt： ICF](opt-optimizations.md) 和 [/ltcg](ltcg-link-time-code-generation.md) 链接器选项，在使用 **/Gw** 选项编译的多个对象文件之间合并可执行文件中的所有相同的只读全局数据。

有关详细信息，请参阅 c + + 团队博客上的 [/Gw 编译器开关简介](https://devblogs.microsoft.com/cppblog/introducing-gw-compiler-switch/) 。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 " **c/c + +** " 文件夹。

1. 选择 " **命令行** " 属性页。

1. 修改 " **附加选项** " 属性以包含 **/Gw** ，然后选择 **"确定"**。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
