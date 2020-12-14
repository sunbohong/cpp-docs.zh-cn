---
description: '了解有关以下内容的详细信息：/Zm (指定预编译头内存分配限制) '
title: /Zm（指定预编译标头的内存分配限额）
ms.date: 03/08/2019
f1_keywords:
- /zm
helpviewer_keywords:
- PCH files, memory allocation limit
- Zm compiler option [C++]
- /Zm compiler option [C++]
- precompiled header files, memory allocation limit
- Specify Precompiled Header Memory Allocation Limit compiler option
- cl.exe compiler, memory allocation limit
- .pch files, memory allocation limit
- memory allocation, Memory Allocation Limit compiler option
- -Zm compiler option [C++]
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
ms.openlocfilehash: 624d8926961d9ca3d32ef204b70683c14dc3197f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224382"
---
# <a name="zm-specify-precompiled-header-memory-allocation-limit"></a>/Zm（指定预编译标头的内存分配限额）

确定编译器分配的用于构造预编译标头的内存量。

## <a name="syntax"></a>语法

```
/Zmfactor
```

## <a name="arguments"></a>参数

*一元*<br/>
一个比例因子，确定编译器用于构造预编译标头的内存量。

*系数* 参数是编译器定义的工作缓冲区的默认大小所占的百分比。 *系数* 的默认值为 100 (百分比) ，但你可以指定更大或更小的数量。

## <a name="remarks"></a>备注

在 Visual Studio 2015 之前的版本中，c + + 编译器使用几个离散堆，每个都有一个有限的限制。 当前，编译器会根据需要动态增加堆，最多可增加到总堆大小限制，并允许预编译标头包含多个地址范围。 因此，很少需要 **/zm** 编译器选项。

如果编译器在使用 **/zm** 编译器选项时遇到堆空间不足并且发出 [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)错误消息，则可能是保留了太多的内存。 请考虑删除 **/zm** 选项。

如果编译器发出 [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md)错误消息，则伴随的 [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md)消息会指定通过使用 **/zm** 编译器选项重新编译时要使用的 *因子* 参数。 此消息仅在预编译标头使用时才有意义 `#pragma hdrstop` 。 在其他情况下，它是由 Windows 虚拟内存压力问题导致的虚假错误，应忽略使用 **/zm** 选项的建议。 相反，当使用 **/maxcpucount** 选项与 **/mp** 选项一起 MSBUILD.EXE 以 CL.EXE 时，请考虑减少并行进程的数目。 有关详细信息，请参阅 [预编译标头 (PCH) 问题和建议](https://devblogs.microsoft.com/cppblog/precompiled-header-pch-issues-and-recommendations/)。

下表显示如果假设默认预编译标头缓冲区的大小为 75 MB，则 *系数* 参数如何影响内存分配限制。

|*系数* 值|内存分配限制|
|-----------------------|-----------------------------|
|10|7.5 MB|
|100|75 MB|
|200|150 MB|
|1000|750 MB|
|2000|1500 MB|

## <a name="other-ways-to-set-the-memory-allocation-limit"></a>设置内存分配限制的其他方式

### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置 /Zm 编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 在导航窗格中，选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**"。

1. 在 "**附加选项**" 框中输入 **/zm** 编译器选项。

### <a name="to-set-the-zm-compiler-option-programmatically"></a>以编程方式设置 /Zm 编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
