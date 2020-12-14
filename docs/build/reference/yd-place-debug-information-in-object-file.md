---
description: '详细了解：/Yd (将调试信息放在对象文件中) '
title: /Yd（将调试信息放在对象文件中）
ms.date: 11/04/2016
f1_keywords:
- /yd
helpviewer_keywords:
- /Yd compiler option [C++]
- -Yd compiler option [C++]
- debugging [C++], debug information files
- Yd compiler option [C++]
ms.assetid: c5a699fe-65ce-461e-964c-7f5eb2a8320a
ms.openlocfilehash: 7716d5ca1893faefac9186f97e2f7439a3887343
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243583"
---
# <a name="yd-place-debug-information-in-object-file"></a>/Yd（将调试信息放在对象文件中）

节奏在与 [/yc](yc-create-precompiled-header-file.md) 和 [/Z7](z7-zi-zi-debug-information-format.md) 选项一起使用时，从预编译头 ( .pch) 文件创建的所有对象文件中完成调试信息。 已弃用。

## <a name="syntax"></a>语法

```
/Yd
```

## <a name="remarks"></a>备注

**/Yd** 已弃用;Visual C++ 现在支持多个对象写入一个 .pdb 文件，请改用 **/zi** 。 有关弃用的编译器选项的列表，请参阅 [按类别列出的编译器选项](compiler-options-listed-by-category.md)中的不 **推荐使用和已删除编译器选项**。

除非需要分发包含调试信息的库，否则请使用 [/zi](z7-zi-zi-debug-information-format.md) 选项，而不是 **/Z7** 和 **/yd**。

在每个 .obj 文件中存储完整的调试信息只是分发包含调试信息的库是必需的。 它会降低编译速度，并需要大量的磁盘空间。 当使用 **/yc** 和 **/Z7** 而不使用 **/yd** 时，编译器会将常见的调试信息存储在从 .pch 文件创建的第一个 .obj 文件中。 编译器不会将此信息插入随后从 .pch 文件创建的 .obj 文件;它将交叉引用插入到信息中。 无论有多少 .obj 文件使用 .pch 文件，只有一个 .obj 文件包含常见的调试信息。

虽然这种默认行为会导致更快的生成时间并减少磁盘空间需求，但如果小的更改需要重新生成包含常见调试信息的 .obj 文件，则不会产生任何影响。 在这种情况下，编译器必须重新生成包含对原始 .obj 文件的交叉引用的所有 .obj 文件。 此外，如果不同的项目使用公用 .pch 文件，则很难依赖于对单个 .obj 文件进行交叉引用。

有关预编译标头的详细信息，请参阅：

- [/Y (预编译标头) ](y-precompiled-headers.md)

- [预编译标头文件](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 点击“命令行”  属性页。

1. 在 **“附加选项”** 框中键入编译器选项。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="examples"></a>示例

假设您有两个基本文件：分别为 node.js 和 G，其中每个文件都包含这些 **#include** 语句：

```
#include "windows.h"
#include "etc.h"
```

下面的命令创建预编译头文件等 .pch 和对象文件的文件：

```
CL /YcETC.H /Z7 F.CPP
```

对象文件 F 包含 WINDOWS .h 的类型和符号信息，以及它们包含的任何其他标头文件 () 。 现在，可以使用预编译标头等 pch 编译源文件 G：

```
CL /YuETC.H /Z7 G.CPP
```

对象文件 G 不包括预编译标头的调试信息，只引用了 F .obj 文件中的信息。 请注意，必须与 F .obj 文件链接。

如果预编译标头不是使用 **/Z7** 编译的，则仍可以在以后使用 **/Z7** 进行编译时使用。 不过，调试信息放在当前的对象文件中，并且在预编译头中定义的函数和类型的本地符号不适用于调试器。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
