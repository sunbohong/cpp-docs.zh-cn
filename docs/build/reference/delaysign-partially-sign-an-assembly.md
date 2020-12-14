---
description: '了解详细信息：/DELAYSIGN (对程序集进行部分签名) '
title: /DELAYSIGN（为程序集进行部分签名）
ms.date: 11/04/2016
f1_keywords:
- /delaysign
- VC.Project.VCLinkerTool.DelaySign
helpviewer_keywords:
- /DELAYSIGN linker option
- DELAYSIGN linker option
- -DELAYSIGN linker option
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
ms.openlocfilehash: 40eeaef958b6a188fd4739fcdc0f5ef5123b220a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201477"
---
# <a name="delaysign-partially-sign-an-assembly"></a>/DELAYSIGN（为程序集进行部分签名）

```
/DELAYSIGN[:NO]
```

## <a name="arguments"></a>参数

**NO**<br/>
指定不应对程序集进行部分签名。

## <a name="remarks"></a>备注

如果只希望将公钥放入程序集中，请使用 **/DELAYSIGN** 。 默认值为 **/DELAYSIGN： NO**。

**/DELAYSIGN** 选项不起作用，除非与 [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)或 [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)一起使用。

在请求完全签名的程序集时，编译器会对包含清单（程序集元数据）的文件进行哈希处理，并使用私钥对哈希进行签名。 产生的数字签名存储在包含清单的文件中。 当延迟对程序集进行签名时，链接器不会计算和存储签名，但会在文件中保留空间，以便以后可以添加签名。

例如，使用 **/DELAYSIGN** 可让测试人员将程序集放入全局缓存中。 测试完成后，可以通过将私钥放置在程序集中来对程序集进行完全签名。

有关对程序集签名的详细信息，请参阅 [强名称程序集 (程序集签名)  (c + +/cli) ](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) 并 [延迟为程序集签名](/dotnet/framework/app-domains/delay-sign-assembly) 。

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
