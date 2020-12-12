---
description: '了解详细信息：/CGTHREADS (编译器线程) '
title: /CGTHREADS（编译器线程）
ms.date: 11/04/2016
helpviewer_keywords:
- /CGTHREADS linker option
- -CGTHREADS linker option
- CGTHREADS linker option
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
ms.openlocfilehash: 71c5031c7013ec6f8ddad153d9cc16bee2004751
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179247"
---
# <a name="cgthreads-compiler-threads"></a>/CGTHREADS（编译器线程）

设置 cl.exe 线程数以在指定链接时代码生成后用于优化和代码生成。

## <a name="syntax"></a>语法

```
/CGTHREADS:[1-8]
```

## <a name="arguments"></a>参数

*数字*<br/>
可供 cl.exe 使用的最大线程数，范围在 1 到 8 之间。

## <a name="remarks"></a>备注

**/CGTHREADS** 选项指定在指定了链接时代码生成 ([/ltcg](ltcg-link-time-code-generation.md)) 时，cl.exe 并行使用的最大线程数，用于编译的优化和代码生成阶段。 默认情况下，cl.exe 使用四个线程，就像指定了 **/CGTHREADS： 4** 一样。 如果有更多处理器内核可用，则较大的 `number` 值可以缩短生成时间。

可为生成指定多个级别的并行。 msbuild.exe 开关 **/maxcpucount** 指定可并行运行的 MSBuild 进程数。 [/Mp (用多个进程生成) ](mp-build-with-multiple-processes.md)编译器标志指定同时编译源文件的 cl.exe 进程的数目。 [/Cgthreads](cgthreads-code-generation-threads.md)编译器选项指定每个 cl.exe 进程使用的线程数。 由于处理器只能同时运行与处理器内核数量相同的线程数，因此同时为所有这些选项指定较大的值将不起作用，而且还会起反作用。 有关如何并行生成项目的详细信息，请参阅 [并行生成多个项目](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild)。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 " **配置属性**"、" **链接器** " 文件夹。

1. 选择 " **命令行** " 属性页。

1. 修改 "**附加选项**" 属性以包含 **/CGTHREADS：** `number` ，其中 `number` 是介于1到8之间的值，然后选择 **"确定"**。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器选项](linker-options.md)<br/>
[MSVC 链接器参考](linking.md)
