---
description: '了解详细信息：/POGOSAFEMODE (在线程安全模式下运行 PGO) '
title: '/POGOSAFEMODE (在线程安全模式下运行 PGO) '
ms.date: 03/14/2018
f1_keywords:
- POGOSAFEMODE
ms.openlocfilehash: dfe8d46a3008a1d41156d077e5b87e50ac345e18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225916"
---
# <a name="pogosafemode-run-pgo-in-thread-safe-mode"></a>/POGOSAFEMODE (在线程安全模式下运行 PGO) 

**从 Visual Studio 2015 开始，已弃用/POGOSAFEMODE 选项**。 改为使用 [/GENPROFILE： EXACT](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) 和 **/GENPROFILE： NOEXACT** 选项。 **/POGOSAFEMODE** 链接器选项指定将创建检测的生成，以便在按配置文件优化过程中将线程安全模式用于分析数据捕获， (PGO) 定型运行。

## <a name="syntax"></a>语法

> **/POGOSAFEMODE**

## <a name="remarks"></a>备注

按配置优化 (PGO) 在分析阶段有两种可能的模式：快速模式  和安全模式  。 当分析处于快速模式时，它会使用增量指令来增加数据计数器。 递增指令速度更快，但不是线程安全的。 当分析处于安全模式时，它将使用联锁增量指令来增加数据计数器。 此指令的功能与增量指令具有相同的功能，并且是线程安全的，但速度较慢。

**/POGOSAFEMODE** 选项将检测生成设置为使用安全模式。 仅当在 PGO 检测链接器阶段指定了弃用的 [/ltcg： PGINSTRUMENT](ltcg-link-time-code-generation.md) 时，才能使用此选项。

默认情况下，PGO 分析在快速模式下运行。 仅当要使用安全模式时，才需要 **/POGOSAFEMODE** 。

若要在安全模式下运行 PGO 分析，必须使用 **/GENPROFILE： EXACT** (首选) ，或使用环境变量 [PogoSafeMode](../environment-variables-for-profile-guided-optimizations.md) 或链接器开关 **/POGOSAFEMODE**，具体取决于系统。 如果要在 x64 计算机上执行分析，则必须使用链接器开关。 如果要在 x86 计算机上执行分析，可以在启动 PGO 检测过程之前，使用链接器开关或将环境变量定义为任意值。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**  >  **链接器**  >  **优化**" 属性页。

1. 在 " **链接时间代码生成** " 属性中，选择 " **按配置优化-检测 (/ltcg： PGInstrument)**"。

1. 选择“配置属性” > “链接器” > “命令行”属性页    。

1. 在 "**附加选项**" 框中输入 **/POGOSAFEMODE** 选项。 选择“确定”以保存更改  。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[/GENPROFILE 和 /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[按配置优化](../profile-guided-optimizations.md)<br/>
[用于 Profile-Guided 优化的环境变量](../environment-variables-for-profile-guided-optimizations.md)<br/>
