---
description: '了解详细信息：/KEYFILE (指定密钥或密钥对以对程序集进行签名) '
title: /KEYFILE（指定密钥或密钥对以便为程序集签名）
ms.date: 11/04/2016
f1_keywords:
- /keyfile
- VC.Project.VCLinkerTool.KeyFile
helpviewer_keywords:
- /KEYFILE linker option
- -KEYFILE linker option
- KEYFILE linker option
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
ms.openlocfilehash: 23c4962ab57688f5d8c1af27fd412d7d36be01a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191155"
---
# <a name="keyfile-specify-key-or-key-pair-to-sign-an-assembly"></a>/KEYFILE（指定密钥或密钥对以便为程序集签名）

```
/KEYFILE:filename
```

## <a name="arguments"></a>参数

*filename*<br/>
包含密钥的文件。 如果包含空格，则将字符串放在双引号中 ( "" ) 。

## <a name="remarks"></a>备注

链接器将公钥插入程序集清单中，然后用私钥对最终程序集进行签名。 若要生成密钥文件，请在命令行中键入 [sn-k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* 。 已签名的程序集被称为具有强名称。

如果使用 [/LN](ln-create-msil-module.md)进行编译，则密钥文件的名称将保存在模块中，并将其合并到程序集中，该程序集包含对模块的显式引用，通过 [#using](../../preprocessor/hash-using-directive-cpp.md)或链接到 [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)时创建的程序集。

还可以通过 [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)将加密信息传递给链接器。 如果需要部分签名的程序集，请使用 [/DELAYSIGN](delaysign-partially-sign-an-assembly.md) 。 有关对程序集签名的详细信息，请参阅 [强名称程序集 (程序集签名)  (c + +/cli) ](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) 。

如果 **/KEYFILE** 和 **/KEYCONTAINER** 都 (通过命令行选项或自定义特性) 来指定，则链接器将首先尝试密钥容器。 如果成功，则使用密钥容器中的信息对程序集签名。 如果链接器找不到密钥容器，它将尝试用/KEYFILE. 指定的文件。 如果成功，则使用密钥文件中的信息对程序集签名，并且将密钥信息安装到密钥容器中（类似于 sn -i），以便在下一次编译中，密钥容器选项将生效。

请注意，密钥文件可能仅包含公钥。

有关对程序集签名的详细信息，请参阅[创建和使用具有强名称的程序集](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)。

影响程序集生成的其他链接器选项包括：

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

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
