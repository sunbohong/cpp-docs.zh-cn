---
description: '了解详细信息：/ASSEMBLYLINKRESOURCE (链接到 .NET Framework 资源) '
title: /ASSEMBLYLINKRESOURCE（链接到 .NET Framework 资源）
ms.date: 11/04/2016
f1_keywords:
- /ASSEMBLYLINKRESOURCE
- VC.Project.VCLinkerTool.AssemblyLinkResource
helpviewer_keywords:
- -ASSEMBLYLINKRESOURCE linker option
- ASSEMBLYLINKRESOURCE linker option
- /ASSEMBLYLINKRESOURCE linker option
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
ms.openlocfilehash: 32761cb16e8428d5e3c18330dffb49a50a42903c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183004"
---
# <a name="assemblylinkresource-link-to-net-framework-resource"></a>/ASSEMBLYLINKRESOURCE（链接到 .NET Framework 资源）

```
/ASSEMBLYLINKRESOURCE:filename
```

## <a name="arguments"></a>参数

*filename*<br/>
希望从程序集链接到的 .NET Framework 资源文件。

## <a name="remarks"></a>备注

/ASSEMBLYLINKRESOURCE 选项创建指向输出文件中 .NET Framework 资源的链接;资源文件不会放入输出文件中。 [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md) 将资源文件嵌入到输出文件中。

当通过链接器创建时，链接的资源在程序集中是公共的。

/ASSEMBLYLINKRESOURCE 要求编译包含 [/clr](clr-common-language-runtime-compilation.md);不允许将 [/LN](ln-create-msil-module.md) 或 [/NOASSEMBLY](noassembly-create-a-msil-module.md) 与/ASSEMBLYLINKRESOURCE. 一起使用

如果 *filename* 是 .NET Framework 资源文件创建的，例如，通过 [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) 或在开发环境中，则可以使用 **system.exception 命名空间中的成员** 进行访问。 有关详细信息，请参阅 [system.object](/dotnet/api/system.resources.resourcemanager)。 对于所有其他资源，请使用 **GetManifestResource** \* 类中的方法在运行时访问资源。

*filename* 可以是任何文件格式。 例如，你可能想要使本机 DLL 成为程序集的一部分，因此可以将它安装到全局程序集缓存中，并从程序集中的托管代码访问它。

影响程序集生成的其他链接器选项包括：

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 点击“命令行”  属性页。

1. 在 " **附加选项** " 框中键入选项。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
