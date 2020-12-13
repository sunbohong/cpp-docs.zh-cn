---
description: '了解详细信息：/V (版本号) '
title: /V（版本号）
ms.date: 11/04/2016
f1_keywords:
- /v
helpviewer_keywords:
- embedding version strings
- /V compiler option [C++]
- version numbers, specifying for .obj
- V compiler option [C++]
- -V compiler option [C++]
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
ms.openlocfilehash: 5025642d4ae30315d24754a7ee46268050cfb22a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187047"
---
# <a name="v-version-number"></a>/V（版本号）

已弃用。 将文本字符串嵌入到 .obj 文件中。

## <a name="syntax"></a>语法

```
/Vstring
```

## <a name="arguments"></a>参数

*string*<br/>
一个字符串，指定要嵌入到 .obj 文件中的版本号或版权声明。

## <a name="remarks"></a>备注

字符串使用版本号或版权声明标记 .obj 文件。 任何空格或制表符必须括在双引号中， ( ") 如果它们是字符串的一部分。 反斜杠 (\\) 必须在双引号后面（如果这些引号是字符串的一部分）。 **/V** 与之间的空格 `string` 是可选的。

您还可以将 [注释 (C/c + +) ](../../preprocessor/comment-c-cpp.md) 与编译器注释类型参数一起使用，以便将编译器的名称和版本号置于 .obj 文件中。

从 Visual Studio 2005 开始，已弃用 **/v** 选项， **/V** 主要用于支持 (vxd) 生成虚拟设备驱动程序，并且 Visual C++ 工具集不再支持构建 vxd。 有关弃用的编译器选项的列表，请参阅 [按类别列出的编译器选项](compiler-options-listed-by-category.md)中的不 **推荐使用和已删除编译器选项**。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 点击“命令行”  属性页。

1. 在 **“附加选项”** 框中键入编译器选项。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
