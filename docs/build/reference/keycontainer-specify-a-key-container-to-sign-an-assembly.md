---
description: '了解详细信息：/KEYCONTAINER (指定用于对程序集进行签名的密钥容器) '
title: /KEYCONTAINER（指定密钥容器以便为程序集签名）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.KeyContainer
- /keycontainer
helpviewer_keywords:
- KEYCONTAINER linker option
- /KEYCONTAINER linker option
- -KEYCONTAINER linker option
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
ms.openlocfilehash: 5f32fdc5400103d4038139fa2dfe9409c9740236
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199579"
---
# <a name="keycontainer-specify-a-key-container-to-sign-an-assembly"></a>/KEYCONTAINER（指定密钥容器以便为程序集签名）

```
/KEYCONTAINER:name
```

## <a name="arguments"></a>参数

*name*<br/>
包含密钥的容器。 如果包含空格，则将字符串放在双引号中 ( "" ) 。

## <a name="remarks"></a>备注

链接器通过将公钥插入程序集清单，并使用私钥对最终程序集进行签名来创建签名的程序集。 若要生成密钥文件，请在命令行中键入 [sn-k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* 。 **sn-i** 将密钥对安装到容器中。

如果使用 [/LN](ln-create-msil-module.md)进行编译，则密钥文件的名称将保存在模块中，并将其合并到程序集中，该程序集包含对模块的显式引用，通过 [#using](../../preprocessor/hash-using-directive-cpp.md)或链接到 [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)时创建的程序集。

还可以通过 [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)将加密信息传递给编译器。 如果需要部分签名的程序集，请使用 [/DELAYSIGN](delaysign-partially-sign-an-assembly.md) 。 有关对程序集签名的详细信息，请参阅 [强名称程序集 (程序集签名)  (c + +/cli) ](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) 。

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
