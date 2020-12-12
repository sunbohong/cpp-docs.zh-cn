---
description: 了解详细信息：管理库
title: 管理库
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLibrarianTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLibrarianTool.AdditionalDependencies
- VC.Project.VCLibrarianTool.RemoveObjects
- VC.Project.VCLibrarianTool.LibraryPaths
- VC.Project.VCLibrarianTool.OutputFile
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryNames
- VC.Project.VCLibrarianTool.AdditionalLibraryDirectories
- VC.Project.VCLibrarianTool.ListContentsFile
- VC.Project.VCLibrarianTool.ListContents
- VC.Project.VCLibrarianTool.SubSystemVersion
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryName
- VC.Project.VCLibrarianTool.SubSystem
helpviewer_keywords:
- /LIBPATH library manager option
- OUT library manager option
- CONVERT library manager option
- LIBPATH library manager option
- /LIST library manager option
- object files, building and modifying
- -LINK50COMPAT library manager option
- REMOVE library manager option
- SUBSYSTEM library manager option
- /LINK50COMPAT library manager option
- /OUT library manager option
- LIB [C++], managing COFF libraries
- -CONVERT library manager option
- LINK50COMPAT library manager option
- -OUT library manager option
- -REMOVE library manager option
- -LIST library manager option
- /SUBSYSTEM library manager option
- -SUBSYSTEM library manager option
- /REMOVE library manager option
- -LIBPATH library manager option
- object files
- LIST library manager option
- /CONVERT library manager option
ms.assetid: f56a8b85-fbdc-4c09-8d8e-00f0ffe1da53
ms.openlocfilehash: f862dfd460bb51cdf6e855c87b08b7426a5642d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199124"
---
# <a name="managing-a-library"></a>管理库

LIB 的默认模式是生成或修改 COFF 对象的库。 如果未指定/EXTRACT (要将对象复制到文件) 或/DEF (以生成导入库) ，则 LIB 在此模式下运行。

若要从对象和/或库生成库，请使用以下语法：

```
LIB [options...] files...
```

此命令从一个或多个输入 *文件* 创建库。 这些 *文件* 可以是 COFF 对象文件、32位 OMF 对象文件或现有的 COFF 库。 LIB 创建一个库，其中包含指定文件中的所有对象。 如果输入文件是32位 OMF 对象文件，则在生成库之前，LIB 会将其转换为 COFF。 LIB 无法接受由16位版本的 LIB 创建的库中的32位 OMF 对象。 必须先使用16位 LIB 来提取对象;然后，可以使用提取的对象文件作为32位 LIB 的输入。

默认情况下，LIB 使用第一个对象或库文件的基名称和扩展名 .lib 来命名输出文件。 输出文件放在当前目录中。 如果已存在具有相同名称的文件，则输出文件将替换现有文件。 若要保留现有库，请使用/OUT 选项指定输出文件的名称。

以下选项适用于生成和修改库：

**/LIBPATH：** *dir*<br/>
重写环境库路径。 有关详细信息，请参阅 LINK [/LIBPATH](libpath-additional-libpath.md) 选项的说明。

**/LIST**<br/>
显示有关输出库到标准输出的信息。 可以将输出重定向到文件。 可以使用/LIST 来确定现有库的内容，而无需对其进行修改。

**/NAME：** *文件名*<br/>
生成导入库时，指定正在为其生成导入库的 DLL 的名称。

**/NODEFAULTLIB**<br/>
在解析外部引用时，从它搜索的库列表中删除一个或多个默认库。 有关详细信息，请参阅 [/NODEFAULTLIB](nodefaultlib-ignore-libraries.md) 。

**/Out：** *filename*<br/>
重写默认输出文件名。 默认情况下，将在当前目录中创建输出库，并在命令行和扩展名 .lib 上创建第一个库或对象文件的基名称。

**/Remove：** *对象*<br/>
省略输出库中的指定 *对象* 。 LIB 通过组合 (对象文件或库中的所有对象) ，然后删除使用/REMOVE. 指定的任何对象，来创建输出库。

**/SUBSYSTEM：**{**CONSOLE** &#124; **EFI_APPLICATION** &#124; **EFI_BOOT_SERVICE_DRIVER** &#124; **EFI_ROM &#124; EFI_RUNTIME_DRIVER** &#124;**本机**&#124; **POSIX** &#124; **WINDOWS** &#124; **WINDOWSCE**} [，# [. # #]] <br/>
告知操作系统如何运行通过链接到输出库而创建的程序。 有关详细信息，请参阅 LINK [/SUBSYSTEM](subsystem-specify-subsystem.md) 选项的说明。

在命令行中指定的 LIB 选项不区分大小写。

可以使用 LIB 执行以下库管理任务：

- 若要将对象添加到库，请为现有库指定文件名，并为新对象指定文件名。

- 若要合并库，请指定库文件名。 可以添加对象并将库与单个 LIB 命令组合使用。

- 若要将库成员替换为新的对象，请指定包含要替换的成员对象的库，以及新对象 (或包含它的库) 的文件名。 当多个输入文件中存在具有相同名称的对象时，LIB 会将 LIB 命令中指定的最后一个对象放入输出库。 替换库成员时，请确保在包含旧对象的库之后指定新的对象或库。

- 若要从库中删除成员，请使用/REMOVE 选项。 在合并所有输入对象之后，LIB 处理任何规范，而不考虑命令行顺序。

> [!NOTE]
> 不能删除成员并将其提取到同一步骤中的文件。 必须先使用/EXTRACT 提取成员对象，然后使用/REMOVE. 再次运行 LIB 此行为不同于其他 Microsoft 产品中提供的 OMF 库) 的16位 LIB (的行为。

## <a name="see-also"></a>请参阅

[LIB 引用](lib-reference.md)
