---
description: '详细了解：/Qimprecise_fwaits (在 Try 块内删除 fwaits) '
title: /Qimprecise_fwaits（移除 Try 块中的 fwaits）
ms.date: 11/04/2016
f1_keywords:
- /Qimprecise_fwaits
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
ms.openlocfilehash: 5f3d96656d062a7e5b0c4ad78ba7cd536069e013
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225617"
---
# <a name="qimprecise_fwaits-remove-fwaits-inside-try-blocks"></a>/Qimprecise_fwaits（移除 Try 块中的 fwaits）

`fwait` **`try`** 使用 [/fp： except](fp-specify-floating-point-behavior.md)编译器选项时，删除内部的块命令。

## <a name="syntax"></a>语法

```
/Qimprecise_fwaits
```

## <a name="remarks"></a>备注

如果 **/fp：除外** ，则此选项不起作用。 如果指定 **/fp： except** 选项，则编译器将 `fwait` 在块中的每个代码行的周围插入一个命令 **`try`** 。 通过这种方式，编译器可以确定产生异常的特定代码行。 **/Qimprecise_fwaits** 删除内部 `fwait` 指令，只保留块周围的等待 **`try`** 。 这样可以提高性能，但编译器将只能表达哪个 **`try`** 块导致了异常，而不是哪一行。

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
