---
description: '详细了解：/favor (优化体系结构细节) '
title: /favor（针对体系结构详细信息优化）
ms.date: 11/04/2016
f1_keywords:
- /favor
helpviewer_keywords:
- -favor compiler option [C++]
- /favor compiler option [C++]
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
ms.openlocfilehash: 184e81e1007214a09088601b6c579692a0dd20a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192299"
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor（针对体系结构详细信息优化）

**/favor：** `option` 生成针对特定体系结构或针对 AMD 和 Intel 体系结构中的微体系结构的细节优化的代码。

## <a name="syntax"></a>语法

> **/favor：**{**blend**  |  **ATOM**  |  **AMD64**  |  **INTEL64**}

## <a name="remarks"></a>备注

**/favor： blend**<br/>
（x86 和 x64）生成针对 AMD 和 Intel 体系结构中的微体系结构的特性进行了优化的代码。 尽管 **/favor： blend** 可能无法在特定处理器上获得最佳性能，但它旨在在各种 x86 和 x64 处理器上给予最佳性能。 默认情况下， **/favor： blend** 有效。

**/favor： ATOM**<br/>
（x86 和 x64）生成针对 Intel Atom 处理器和 Intel Centrino Atom 处理器的特性进行了优化的代码。 使用 **/favor： ATOM** 生成的代码可能还会对 intel 处理器产生 intel SSSE3、SSE3、SSE2 和 SSE 指令。

**/favor： AMD64**<br/>
（仅限 x64）针对 AMD Opteron 和支持 64 位扩展的 Athlon 处理器优化生成的代码。 优化过的代码可在所有 x64兼容平台上运行。 使用 **/favor： AMD64** 生成的代码可能会导致支持 Intel64 的 Intel 处理器上性能更差。

**/favor： INTEL64**<br/>
（仅限 x64）针对支持 Intel64 的 Intel 处理器优化生成的代码，这通常能提高平台的性能。 生成的代码可在任何 x64 平台上运行。 用 **/favor： INTEL64** 生成的代码可能会导致 AMD 皓龙上的性能较差，以及支持64位扩展的速龙处理器。

> [!NOTE]
> Intel64 体系结构之前称为扩展内存64技术，相应的编译器选项为 **/favor： EM64T**。

有关如何为 x64 体系结构编程的信息，请参阅 [X64 软件约定](../x64-software-conventions.md)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 " **c/c + +** " 文件夹。

1. 选择 " **命令行** " 属性页。

1. 在 " **附加选项** " 框中输入编译器选项。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
