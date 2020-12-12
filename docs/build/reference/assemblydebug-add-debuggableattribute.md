---
description: '了解详细信息：/ASSEMBLYDEBUG (Add DebuggableAttribute) '
title: /ASSEMBLYDEBUG（添加 DebuggableAttribute）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.AssemblyDebug
- /ASSEMBLYDEBUG
helpviewer_keywords:
- /ASSEMBLYDEBUG linker option
- -ASSEMBLYDEBUG linker option
- ASSEMBLYDEBUG linker option
ms.assetid: 94443af3-470c-41d7-83a0-7434563d7982
ms.openlocfilehash: 7d63ae4ffd86099147b076a499321ed5dcf3ca54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183030"
---
# <a name="assemblydebug-add-debuggableattribute"></a>/ASSEMBLYDEBUG（添加 DebuggableAttribute）

```
/ASSEMBLYDEBUG[:DISABLE]
```

/ASSEMBLYDEBUG 发出带有调试信息跟踪的 **DebuggableAttribute** 特性并禁用 JIT 优化。 这与在源中指定以下属性相同：

```
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG
```

/ASSEMBLYDEBUG： DISABLE 发出 **DebuggableAttribute** 属性，但禁用调试信息跟踪并启用 JIT 优化。 这与在源中指定以下属性相同：

```
[assembly:Debuggable(false, false)];   // same as /ASSEMBLYDEBUG:DISABLE
```

默认情况下，不会发出 **DebuggableAttribute** 属性。

还可以直接在源代码中将 DebuggableAttribute 添加到程序集。 例如，应用于对象的

```
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG
```

## <a name="remarks"></a>备注

需要显式指定托管映像可调试。 仅使用 [/zi](z7-zi-zi-debug-information-format.md) 是不够的。

影响程序集生成的其他链接器选项包括：

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **调试** " 属性页。

1. 修改 "可 **调试程序集** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AssemblyDebug%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
