---
description: '了解详细信息：/F (设置堆栈大小) '
title: /F（设置堆栈大小）
ms.date: 11/04/2016
f1_keywords:
- /f
helpviewer_keywords:
- set stack size compiler option
- F compiler option [C++]
- -F compiler option [C++]
- /F compiler option [C++]
- stack, setting size
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
ms.openlocfilehash: 5bf8b0855c65fc39caf8935b06a877c62a4e0df0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200775"
---
# <a name="f-set-stack-size"></a>/F（设置堆栈大小）

设置程序堆栈大小（以字节为单位）。

## <a name="syntax"></a>语法

> **/F** *编号*

## <a name="arguments"></a>参数

*数字*<br/>
堆栈大小（以字节为单位）。

## <a name="remarks"></a>备注

如果没有此选项，堆栈大小默认为 1 MB。 *Number* 参数可以采用 Decimal 或 C 语言表示法。 自变量的范围可以是从1到链接器接受的最大堆栈大小。 链接器将指定的值向上舍入为最接近的4个字节。 **/F** 和 *number* 之间的空格是可选的。

如果程序获取堆栈溢出消息，则可能需要增大堆栈大小。

还可以通过以下方式设置堆栈大小：

- 使用 **/STACK** 链接器选项。 有关详细信息，请参阅 [/STACK](stack.md)。

- 对 .exe 文件使用 EDITBIN。 有关详细信息，请参阅 [EDITBIN Reference](editbin-reference.md)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. 在 **“附加选项”** 框中键入编译器选项。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
