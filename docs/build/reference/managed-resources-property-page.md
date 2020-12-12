---
description: 了解详细信息： "托管资源" 属性页
title: “托管资源”属性页
ms.date: 08/28/2019
f1_keywords:
- VC.Project.VCManagedResourceCompilerTool.ResourceFileName
- VC.Project.VCManagedResourceCompilerTool.OutputFileName
- VC.Project.VCManagedResourceCompilerTool.DefaultLocalizedResources
helpviewer_keywords:
- Managed Resources property page
ms.assetid: 80b80384-ee55-494d-9f0e-907bb98cfc19
ms.openlocfilehash: 42816e2b4625bc5ab4620f4caafb627f55bd9cd5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190713"
---
# <a name="managed-resources-property-page"></a>“托管资源”属性页

在 c + +/CLI 程序中使用 .NET 资源时，" **托管** 资源" 属性页公开了以下托管资源编译器 [resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) 属性：

- **资源逻辑名称**

   指定生成的中间 .resources 文件的逻辑名称。 逻辑名称是用于加载资源的名称。 如果未指定逻辑名称，则使用资源 (.resx) 文件名作为逻辑名称。

- **输出文件名**

   指定此资源 (.resx) 文件构成的最终输出文件的名称。

- **默认本地化资源**

   指定给定的 .resx 文件是构成默认资源还是附属 .dll。

有关如何访问 " **托管资源** " 属性页的信息，请参阅 [在 Visual Studio 中设置 c + + 编译器和生成属性](../working-with-project-properties.md)。

## <a name="see-also"></a>请参阅

[使用 RC（RC 命令行）](/windows/win32/menurc/using-rc-the-rc-command-line-)<br>
[C++ 项目属性页参考](property-pages-visual-cpp.md)<br>
[/ASSEMBLYRESOURCE (嵌入托管资源) ](assemblyresource-embed-a-managed-resource.md)
