---
description: '了解详细信息：/Qpar (自动并行) '
title: /Qpar（自动并行化程序）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
ms.openlocfilehash: f0d4264acc4224aaad518f936dcb885d592d3007
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225578"
---
# <a name="qpar-auto-parallelizer"></a>/Qpar（自动并行化程序）

启用编译器的 [自动并行](../../parallel/auto-parallelization-and-auto-vectorization.md) 功能，以便在代码中自动并行化循环。

## <a name="syntax"></a>语法

```
/Qpar
```

## <a name="remarks"></a>备注

当编译器自动并行化代码中的循环时，它会将计算分布在多个处理器内核中。 仅当编译器确定将循环并行化合法时，才会执行此操作，并且并行化会提高性能。

提供了 `#pragma loop()` 指令来帮助优化程序并行化特定循环。 有关详细信息，请参阅 [循环](../../preprocessor/loop.md)。

有关如何为自动并行启用输出消息的信息，请参阅 [/Qpar-report (自动并行报告级别) ](qpar-report-auto-parallelizer-reporting-level.md)。

### <a name="to-set-the-qpar-compiler-option-in-visual-studio"></a>在 Visual Studio 中设置 /Qpar 编译器选项

1. 在“解决方案资源管理器” 中，打开项目的快捷菜单，然后选择“属性” 。

1. 在 " **属性页** " 对话框中的 " **c/c + +**" 下，选择 " **命令行**"。

1. 在 " **附加选项** " 框中，输入 `/Qpar` 。

### <a name="to-set-the-qpar-compiler-option-programmatically"></a>以编程方式设置 /Qpar 编译器选项

- 使用 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> 中的代码示例。

## <a name="see-also"></a>请参阅

[/Q 选项 (低级别操作) ](q-options-low-level-operations.md)<br/>
[/Qpar-report (自动并行报告级别) ](qpar-report-auto-parallelizer-reporting-level.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)<br/>
[#pragma 循环 ( # B1 ](../../preprocessor/loop.md)<br/>
[Visual Studio 中的本机代码矢量化](/archive/blogs/nativeconcurrency/auto-vectorizer-in-visual-studio-2012-overview)
