---
description: '了解详细信息：/USEPROFILE (在线程安全模式下运行 PGO) '
title: '/USEPROFILE (将 PGO 数据用于 LTCG) '
ms.date: 03/14/2018
f1_keywords:
- USEPROFILE
ms.openlocfilehash: c6c293b8467ea308dc2f7b4a4cd916cc5d9ac4c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247041"
---
# <a name="useprofile-run-pgo-in-thread-safe-mode"></a>/USEPROFILE (在线程安全模式下运行 PGO) 

此链接器选项与 [/ltcg (链接时代码生成](ltcg-link-time-code-generation.md) 通知链接器使用按配置优化 (PGO) 定型数据来生成。

## <a name="syntax"></a>语法

> **/USEPROFILE**[**：**{**主动型** | **PGD =**_filename_}]

### <a name="arguments"></a>参数

**紧**<br/>
此可选参数指定应在优化代码生成过程中使用非常速度优化。

**PGD** =*filename*<br/>
指定 .pgd 文件的基文件名。 默认情况下，链接器使用具有 .pgd 扩展名的基本可执行文件名称。

## <a name="remarks"></a>备注

**/USEPROFILE** 链接器选项与 **/ltcg** 一起使用，可基于 PGO 定型数据生成或更新优化生成。 它等效于弃用的 **/ltcg： PGUPDATE** 和 **/ltcg： PGOPTIMIZE** 选项。

可选的 **主动型** 参数将禁用与大小相关的试探法，以尝试优化速度。 这可能导致优化大幅增加可执行文件的大小，并且可能不会提高生成速度。 你应该分析和比较使用的结果，而不是使用 **主动**。 必须显式指定此参数;默认情况下不启用它。

**PGD** 参数指定要使用的定型数据 .pgd 文件的可选名称，与 [/GENPROFILE 或/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)中的相同。 它与弃用的 **/PGD** 开关等效。 默认情况下，如果未指定 *文件名* ，则使用与可执行文件具有相同基名称的 .pgd 文件。

**/USEPROFILE** 链接器选项是 Visual Studio 2015 中的新增选项。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**  >  **链接器**  >  **优化**" 属性页。

1. 在 " **链接时间代码生成** " 属性中，选择 " **(/Ltcg) 使用链接时间代码生成**"。

1. 选择“配置属性” > “链接器” > “命令行”属性页    。

1. 在 "**附加选项**" 框中输入 **/USEPROFILE** 选项和可选参数。 选择“确定”以保存更改  。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[/GENPROFILE 和 /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[按配置优化](../profile-guided-optimizations.md)<br/>
[用于 Profile-Guided 优化的环境变量](../environment-variables-for-profile-guided-optimizations.md)<br/>
