---
description: '了解详细信息：/homeparams (将寄存器参数复制到堆栈) '
title: /homeparams（将寄存器参数复制到堆栈）
ms.date: 12/17/2018
f1_keywords:
- /homeparams
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
ms.openlocfilehash: 52145534121831be256c3db2a6ccacdffb30b2c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191467"
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams（将寄存器参数复制到堆栈）

强制将传入寄存器的参数写入其在函数入口的堆栈上的位置。

## <a name="syntax"></a>语法

> **/homeparams**

## <a name="remarks"></a>备注

此编译器选项仅适用于面向 x64 的本机和跨平台。

X64 调用约定需要为所有参数分配堆栈空间，即使是在寄存器中传递的参数也是如此。 有关详细信息，请参阅 [参数传递](../../build/x64-calling-convention.md#parameter-passing)。 默认情况下，在发布版本中不会将寄存器参数复制到为其分配的堆栈空间。 这使得调试程序的优化发布版本非常困难。

对于发布版本，你可以使用 **/homeparams** 选项强制编译器将注册参数复制到堆栈，以确保可以调试你的应用程序。 **/homeparams** 确实意味着性能缺点，因为它需要额外的循环来将寄存器参数加载到堆栈上。

在调试版本中，堆栈始终填充寄存器中传递的参数。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 打开 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. 在 " **附加选项** " 框中输入编译器选项。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
