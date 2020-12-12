---
description: '了解更多相关信息：/ASSEMBLYRESOURCE (嵌入托管资源) '
title: /ASSEMBLYRESOURCE（嵌入托管资源）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.EmbedManagedResourceFile
- /ASSEMBLYRESOURCE
helpviewer_keywords:
- ASSEMBLYRESOURCE linker option
- assemblies [C++]
- -ASSEMBLYRESOURCE linker option
- assemblies [C++], linking resource files
- /ASSEMBLYRESOURCE linker option
ms.assetid: 0ce6e1fb-921b-4b1b-a59c-d35388d789f2
ms.openlocfilehash: 3f79cc177df72bb83288a0a229fdf47adb0e7fc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182913"
---
# <a name="assemblyresource-embed-a-managed-resource"></a>/ASSEMBLYRESOURCE（嵌入托管资源）

```
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]
```

## <a name="parameters"></a>parameters

*filename*<br/>
要在此程序集中嵌入的托管资源。

name<br/>
可选。 资源的逻辑名称;用于加载资源的名称。 默认值是文件的名称。

（可选）可以指定文件是否应为程序集清单中的私有文件。 默认情况下， *名称* 在程序集中是公共的。

## <a name="remarks"></a>备注

使用/ASSEMBLYRESOURCE 选项可在程序集中嵌入资源。

当通过链接器创建时，资源在程序集中是公共的。 链接器不允许重命名程序集中的资源。

如果 *filename* 是 .NET Framework 资源 () 文件创建的资源（例如，通过 [资源文件生成器 ( # A0)](/dotnet/framework/tools/resgen-exe-resource-file-generator)或在开发环境中），则可以使用 **system.exception 命名空间中的成员** 访问该资源。有关详细信息，[请参阅。](/dotnet/api/system.resources.resourcemanager) 对于所有其他资源，请使用 **GetManifestResource** \* 类中的方法在运行时访问资源。

影响程序集生成的其他链接器选项包括：

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **输入** " 属性页。

1. 修改 " **嵌入托管资源文件** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
