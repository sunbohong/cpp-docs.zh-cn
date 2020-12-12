---
description: '了解详细信息：/FU (名称强制 #using 文件) '
title: '/FU（命名强制 #using 文件）'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.ForcedUsingFiles
- /FU
- VC.Project.VCNMakeTool.ForcedUsingAssemblies
helpviewer_keywords:
- -FU compiler option [C++]
- FU compiler option [C++]
- /FU compiler option [C++]
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
ms.openlocfilehash: 458369e7ff1322d2d2fa2fb37e8915c5a39c8446
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200372"
---
# <a name="fu-name-forced-using-file"></a>/FU（命名强制 #using 文件）

一种编译器选项，您可以将其用作在源代码中将文件名传递到 [#using 指令](../../preprocessor/hash-using-directive-cpp.md) 的替代方法。

## <a name="syntax"></a>语法

> **/FU** *文件*

## <a name="arguments"></a>参数

*file*<br/>
指定要在此编译中引用的元数据文件。

## <a name="remarks"></a>备注

/FU 开关只采用一个文件名。 若要指定多个文件，请对每个文件使用 /FU。

如果使用 c + +/CLI 并且引用元数据以使用 [友元程序集](../../dotnet/friend-assemblies-cpp.md) 功能，则不能使用 **/FU**。 你必须将 `#using` 与 `[as friend]` 特性一起使用，才能在代码中引用元数据。 Visual C++ 组件扩展 c + +/CX 中不支持友元程序集

有关如何 (CLR) 创建公共语言运行时的程序集或模块，请参阅 [/clr (公共语言运行时编译) ](clr-common-language-runtime-compilation.md)。 有关如何在 c + +/CX 中生成的信息，请参阅 [生成应用和库](../../cppcx/building-apps-and-libraries-c-cx.md)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **高级**" 属性页。

1. 修改 **强制 #using** 属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>。

## <a name="see-also"></a>请参阅

[Output-File (/F) 选项](output-file-f-options.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
