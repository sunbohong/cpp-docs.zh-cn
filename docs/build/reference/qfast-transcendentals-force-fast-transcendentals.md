---
description: '详细了解：/Qfast_transcendentals (强制 Fast 先验) '
title: /Qfast_transcendentals（强制快速先验）
ms.date: 11/04/2016
f1_keywords:
- /Qfast_transcendentals
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
ms.openlocfilehash: 7701925aa7df33107b0829ade1c0c711eda14c08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225656"
---
# <a name="qfast_transcendentals-force-fast-transcendentals"></a>/Qfast_transcendentals（强制快速先验）

生成超越函数的内联代码。

## <a name="syntax"></a>语法

```
/Qfast_transcendentals
```

## <a name="remarks"></a>备注

此编译器选项强制将超越函数转换为内联代码，以提高执行速度。 仅当与 **/fp： except** 或 **/fp：** only 配对时，此选项才有效。 对于超越函数，生成内联代码已经是 **/fp： fast** 下的默认行为。

此选项不兼容 **/fp： strict**。 有关浮点编译器选项的详细信息，请参阅 [/fp (指定 Floating-Point 行为) ](fp-specify-floating-point-behavior.md) 。

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
