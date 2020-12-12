---
description: '了解详细信息：/Ge (启用堆栈探测) '
title: /Ge（启用堆栈探测）
ms.date: 11/04/2016
f1_keywords:
- /ge
helpviewer_keywords:
- -Ge compiler option [C++]
- enable stack probes
- /Ge compiler option [C++]
- stack, stack probes
- stack probes
- stack checking calls
- Ge compiler option [C++]
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
ms.openlocfilehash: db996deb1c5b964661e5465fe72cfb0fab93df56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192013"
---
# <a name="ge-enable-stack-probes"></a>/Ge（启用堆栈探测）

为需要本地变量存储的每个函数调用激活堆栈探测。

## <a name="syntax"></a>语法

```
/Ge
```

## <a name="remarks"></a>备注

如果重写堆栈探测的功能，则此机制很有用。 建议使用 [/Gh (启用 _Penter 挂钩) 函数， ](gh-enable-penter-hook-function.md) 而不是重新编写堆栈探测。

[/Gs (控制堆栈检查调用) ](gs-control-stack-checking-calls.md) 具有相同的效果。

不推荐使用 **/Ge** ;从 Visual Studio 2005 开始，编译器会自动生成堆栈检查。 有关弃用的编译器选项的列表，请参阅 [按类别列出的编译器选项](compiler-options-listed-by-category.md)中的不 **推荐使用和已删除编译器选项**。

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
