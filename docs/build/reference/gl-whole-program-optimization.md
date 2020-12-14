---
description: '了解有关以下内容的详细信息：/GL (完全程序优化) '
title: /GL（全程序优化）
ms.date: 11/04/2016
f1_keywords:
- /gl
helpviewer_keywords:
- /GL compiler option [C++]
- whole program optimizations and C++ compiler
- -GL compiler option [C++]
- GL compiler option [C++]
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
ms.openlocfilehash: ad42eaeeacf897686831c9b415aa62026b5644f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200190"
---
# <a name="gl-whole-program-optimization"></a>/GL（全程序优化）

启用全程序优化。

## <a name="syntax"></a>语法

```
/GL[-]
```

## <a name="remarks"></a>备注

全程序优化允许编译器对程序中的所有模块的信息进行优化。 如果不使用全程序优化，则会在每个模块 (编译单位) 基础上执行优化。

全程序优化默认情况下处于关闭状态，必须显式启用。 但是，也可以通过 **/GL-** 显式禁用该方法。

对于所有模块的信息，编译器可以：

- 优化跨函数边界使用寄存器。

- 更好地跟踪全局数据的修改，从而减少加载和存储的数量。

- 更好地跟踪由指针取消引用修改的可能的项集，从而减少加载和存储的数目。

- 即使在另一个模块中定义函数时，也会在模块中内联该函数。

使用 **/gl** 生成的 .obj 文件将不会提供给 [EDITBIN](editbin-reference.md) 和 [DUMPBIN](dumpbin-reference.md)这样的链接器实用工具。

如果使用 **/gl** 和 [/c](c-compile-without-linking.md)编译程序，则应使用/ltcg 链接器选项来创建输出文件。

[/Zi](z7-zi-zi-debug-information-format.md)不能与 **/gl** 一起使用

在当前版本中使用 **/gl** 生成的文件格式可能无法由 Visual C++ 的后续版本读取。 你不应提供由使用 **/gl** 生成的 .obj 文件组成的 .lib 文件，除非你愿意为你希望用户使用、现在和将来的所有版本的 Visual C++ 提供 .lib 文件的副本。

使用 **/gl** 和预编译头文件生成的 .obj 文件不应用于生成 .lib 文件，除非该 .lib 文件将链接到生成 **/gl** .obj 文件的同一计算机上。 链接时需要 .obj 文件的预编译头文件中的信息。

有关中提供的优化和全程序优化的限制的详细信息，请参阅 [/ltcg](ltcg-link-time-code-generation.md)。  **/Gl** 还可以提供按配置优化;请参阅/LTCG。  在针对按配置优化进行编译时，如果想要从按配置优化的函数进行排序，则必须使用 [/gy](gy-enable-function-level-linking.md) 或表示/Gy. 的编译器选项进行编译

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 有关如何在开发环境中指定 **/gl** 的信息，请参阅 [/ltcg (链接时间代码生成)](ltcg-link-time-code-generation.md) 。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
