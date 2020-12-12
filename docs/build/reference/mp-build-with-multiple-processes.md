---
description: '了解有关以下内容的详细信息：/MP (具有多个进程的生成) '
title: /MP（使用多个进程生成）
ms.date: 04/08/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.MultiProcessorCompilation
helpviewer_keywords:
- -MP compiler option (C++)
- /MP compiler option (C++)
- MP compiler option (C++)
- cl.exe compiler, multi-process build
ms.openlocfilehash: d5d4441be505dfc1251b099aa95a6ce1544289ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137782"
---
# <a name="mp-build-with-multiple-processes"></a>/MP（使用多个进程生成）

**/MP** 选项可缩短在命令行上编译源文件的总时间。 **/MP** 选项将使编译器在每个单独进程中创建一个或多个自身副本。 然后，这些副本将同时编译源文件。 因此，可以显著减少生成源文件的总时间。

## <a name="syntax"></a>语法

> **/Mp**[*processMax*]

## <a name="arguments"></a>参数

*processMax*<br/>
（可选）编译器可以创建的最大进程数。

*ProcessMax* 参数的范围必须介于1到65536之间。 否则，编译器会发出警告消息 **D9014**，忽略 *processMax* 参数，并假定最大进程数为1。

如果省略 *processMax* 参数，编译器会从操作系统检索计算机上 [有效处理器](#effective_processors) 的数目，并为每个处理器创建一个进程。

## <a name="remarks"></a>备注

**/MP** 编译器选项可以在编译多个文件时显著缩短生成时间。 为了缩短生成时间，编译器将创建最多 *processMax* 的副本，然后使用这些副本来编译您的源文件。 **/MP** 选项适用于编译，但不适用于链接或链接时间代码生成。 默认情况下， **/MP** 选项处于关闭状态。

生成时间的改善取决于计算机上的处理器数、要编译的文件数以及系统资源可用性，如 I/O 容量。 试验 **/MP** 选项，以确定生成特定项目的最佳设置。 获取帮助你做出决定的建议，请参阅 [准则](#guidelines)。

## <a name="incompatible-options-and-language-features"></a>不兼容的选项和语言功能

**/MP** 选项与一些编译器选项和语言功能不兼容。 如果将不兼容的编译器选项与 **/mp** 选项一起使用，编译器会发出警告 **D9030** 并忽略 **/mp** 选项。 如果使用不兼容的语言功能，编译器会发出错误 [C2813](../../error-messages/compiler-errors-2/compiler-error-c2813.md) ，然后结束或继续，具体取决于当前编译器警告等级选项。

> [!NOTE]
> 大多数选项不兼容，因为如果允许这些选项，并发执行的编译器会将其输出同时写入控制台或特定文件。 因此，输出会互相混合，产生混淆。 在某些情况下，选项组合会使性能变得更糟。

下表列出了与 **/MP** 选项不兼容的编译器选项和与语言功能：

|选项或语言功能|描述|
|--------------------------------|-----------------|
|[#import](../../preprocessor/hash-import-directive-cpp.md) 预处理器指令|将类型库中的类型转换为 C++ 类，然后将这些类写入头文件。|
|[/E](e-preprocess-to-stdout.md), [/EP](ep-preprocess-to-stdout-without-hash-line-directives.md)|将预处理器输出复制到标准输出 (**stdout**)。|
|[/Gm](gm-enable-minimal-rebuild.md)|已弃用。 启用增量重新生成。|
|[/showIncludes](showincludes-list-include-files.md)|将包含文件的列表写入标准错误 (**stderr**)。|
|[/Yc](yc-create-precompiled-header-file.md)|编写预编译头文件。|

## <a name="diagnostic-messages"></a>诊断消息

如果指定与 **/MP** 选项不兼容的选项或语言功能，将收到一条诊断消息。 下表列出了编译器的消息和行为：

|诊断消息|描述|编译器行为|
|------------------------|-----------------|-----------------------|
|**C2813**|**#Import** 指令与 **/MP** 选项不兼容。|除非另外指定了 [编译器警告等级](compiler-option-warning-level.md) 选项，否则编译终止。|
|**D9014**|为 *processMax* 参数指定的值无效。|编译器将忽略无效值，并假定值为 1。|
|**D9030**|指定选项与 **/MP** 不兼容。|编译器会忽略 **/MP** 选项。|

## <a name="guidelines"></a><a name="guidelines"></a> 准则

### <a name="measure-performance"></a>测量性能

使用总生成时间来测量性能。 可以使用物理时钟测量生成时间，或使用能够计算生成启动和停止之间的时间差的软件。 如果计算机具有多个处理器，物理时钟测量结果可能会比软件时间测量结果更准确。

### <a name="effective-processors"></a><a name="effective_processors"></a> Effective Processors

对于其每个物理处理器，计算机可以有一个或多个虚拟处理器（也称为 *有效处理器*）。 每个物理处理器可具有一个或多个核心，如果操作系统为核心启用了超线程，则类似于每个核心具有两个虚拟处理器。

例如，如果某计算机具有一个物理处理器，该物理处理器有一个核心，并且禁用了超线程，则这台计算机具有一个有效处理器。 相反，如果某计算机具有两个物理处理器，每个物理处理器有两个核心，且所有核心均已启用超线程，则这台计算机具有八个有效处理器。 也就是说， (8 个有效处理器) = (2 个物理处理器，每个物理处理器) x (2 个核心，因为超线程) 。

如果省略 **/mp** 选项中的 *processMax* 参数，编译器会从操作系统获取有效处理器数目，然后为每个有效处理器创建一个进程。 但是，编译器无法保证特定处理器上执行的是哪个进程；该决策由操作系统做出。

### <a name="number-of-processes"></a>进程数

编译器计算将用于编译源文件的进程数。 该值是在命令行上指定的源文件数和使用 **/MP** 选项显式或隐式指定的进程数中较小的值。 如果提供 **/mp** 选项的 *processMax* 参数，则可以显式设置最大进程数。 如果省略 *processMax* 参数，则可以使用默认值，该默认值等于计算机中的有效处理器数。

例如，假设指定以下命令行：

`cl /MP7 a.cpp b.cpp c.cpp d.cpp e.cpp`

在本例中，编译器使用五个进程，因为它是五个源文件和最多七个进程中的较小值。 或者，假设计算机具有两个有效处理器，并且指定以下命令行：

`cl /MP a.cpp b.cpp c.cpp`

在本例中，操作系统报告两个处理器，于是编译器在计算过程中使用两个进程。 因此，编译器将使用两个进程执行生成，因为它是两个进程和三个源文件中的较小值。

### <a name="source-files-and-build-order"></a>源文件和生成顺序

可能无法按照源文件显示在命令行上的相同顺序对源文件进行编译。 虽然编译器创建了一组包含编译器副本的进程，但由操作系统安排每个进程的执行时间。 因此，无法保证按特定顺序编译源文件。

在有可用于编译源文件的进程时编译源文件。 如果文件多于进程数，则可用进程会编译第一组文件。 当进程处理完以前的文件并可处理其中一个剩余文件时，将处理剩余的文件。

不要在命令行上多次指定同一源文件。 例如，如果某工具自动创建基于项目中依赖项信息的 [](contents-of-a-makefile.md) ，可能会发生这种情况。 如果未指定 **/MP** 选项，编译器将按顺序处理文件列表，并重新编译每个出现的文件。 但是，如果指定了 **/MP** 选项，不同的编译器可能会同时编译相同的文件。 因此，不同的编译器将尝试同时写入相同的输出文件。 某个编译器将获得对输出文件独占写入访问权限并成功完成写入，而其他编译器则会失败并出现文件访问错误。

### <a name="using-type-libraries-import"></a>使用类型库 (#import)

编译器不支持通过 [/MP](../../preprocessor/hash-import-directive-cpp.md) 开关使用 **#import** 指令。 如果可能，请执行以下步骤解决此问题：

- 将各种源文件中的所有 `#import` 指令指令移动到一个或多个文件，然后关闭 **/MP** 选项编译这些文件。 将生成一组头文件。

- 在剩余的源文件中，插入指定生成头文件 [#include](../../preprocessor/hash-include-directive-c-cpp.md) 指令，然后使用 **/MP** 选项编译剩余源文件。

### <a name="visual-studio-project-settings"></a>Visual Studio 项目设置

#### <a name="the-msbuildexe-tool"></a>MSBUILD.exe 工具

Visual Studio 使用 [MSBuild.exe](/visualstudio/msbuild/msbuild-reference) 工具来生成解决方案和项目。 MSBuild.exe 工具的 **/maxcpucount：**_number_ (或 **/m：**_number_) 命令行选项可以同时生成多个项目。 **/MP** 编译器选项可以同时生成多个编译单元。 如果它适用于你的应用程序，可以使用 **/MP** 和/或 **/maxcpucount** 缩短解决方案生成时间。

解决方案生成时间在一定程度上取决于执行生成的进程数。 [/Maxcpucount](/visualstudio/msbuild/msbuild-command-line-reference) MSBuild 选项的 *number* 参数指定同时生成的最大项目数。 同样， **/mp** 编译器选项的 *processMax* 参数指定同时生成的最大编译单元数。 如果 **/maxcpucount** 选项指定了 *P* 项目， **/Mp** 选项指定了 *C* 进程，则最多同时执行 *P* x *c* 进程。

用于决定是使用 MSBuild 还是 **/mp** 技术的准则如下所示：

- 如果有很多项目在每个项目中都有几个文件，请使用 MSBuild 工具。

- 如果项目较少，而每个项目中有许多文件，请使用 **/MP** 选项。

- 如果项目数和每个项目的文件数达到平衡，则同时使用 MSBuild 和 **/mp**。 起初，将 **/maxcpucount** 选项设置为要生成的项目数，并将 **/MP** 选项设置为计算机上的处理器数。 测量性能，然后调整设置以生成最佳结果。 重复此过程，直到对总生成时间感到满意。

## <a name="see-also"></a>请参阅

[#import 指令](../../preprocessor/hash-import-directive-cpp.md)<br/>
[命令行参考](/visualstudio/msbuild/msbuild-command-line-reference)<br/>
[/Zf（更快的 PDB 生成）](zf.md)<br/>
