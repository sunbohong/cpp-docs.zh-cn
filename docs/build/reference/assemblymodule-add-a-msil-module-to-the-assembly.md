---
description: '了解详细信息：/ASSEMBLYMODULE (向程序集添加 MSIL 模块) '
title: /ASSEMBLYMODULE（向程序集添加 MSIL 模块）
ms.date: 11/04/2016
f1_keywords:
- /assemblymodule
- VC.Project.VCLinkerTool.AddModuleNamesToAssembly
helpviewer_keywords:
- ASSEMBLYMODULE linker option
- assemblies [C++], adding modules to
- assemblies [C++]
- /ASSEMBLYMODULE linker option
- -ASSEMBLYMODULE linker option
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
ms.openlocfilehash: d56895b6bec05efda1104e319e93a040f818e06e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182939"
---
# <a name="assemblymodule-add-a-msil-module-to-the-assembly"></a>/ASSEMBLYMODULE（向程序集添加 MSIL 模块）

```
/ASSEMBLYMODULE:filename
```

## <a name="arguments"></a>参数

*filename*<br/>
要包括在此程序集中的模块。

## <a name="remarks"></a>备注

使用/ASSEMBLYMODULE 选项，可以将模块引用添加到程序集。 模块中的类型信息将不可用于添加了模块引用的程序集程序。 但是，模块中的类型信息将可用于引用该程序集的任何程序。

使用 [#using](../../preprocessor/hash-using-directive-cpp.md) 将模块引用添加到程序集，并使模块的类型信息可用于程序集程序。

例如，考虑以下情况：

1. 使用 [/LN](ln-create-msil-module.md)创建模块。

1. 在其他项目中使用/ASSEMBLYMODULE，以在当前编译中包含该模块，这将创建一个程序集。 此项目不会引用模块 `#using` 。

1. 引用此程序集的任何项目现在还可以使用模块中的类型。

影响程序集生成的其他链接器选项包括：

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

MSVC 链接器接受. .netmodule 文件作为输入，并且链接器生成的输出文件将是程序集或 .netmodule，它对任何已输入到链接器的 netmodule 都没有运行时依赖关系。  有关详细信息，请参阅 [用作链接器输入的 .netmodule 文件](netmodule-files-as-linker-input.md)。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **输入** " 属性页。

1. 修改 " **将模块添加到程序集** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
