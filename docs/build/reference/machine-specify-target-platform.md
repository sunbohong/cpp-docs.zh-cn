---
description: '了解详细信息：/MACHINE (指定目标平台) '
title: /MACHINE（指定目标平台）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.TargetMachine
- /machine
helpviewer_keywords:
- mapfiles, creating linker
- target platform
- -MACHINE linker option
- /MACHINE linker option
- MACHINE linker option
ms.assetid: 8d41bf4b-7e53-4ab9-9085-d852b08d31c2
ms.openlocfilehash: a1bf87142fb99577672391356a43a2771ea0b09f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190804"
---
# <a name="machine-specify-target-platform"></a>/MACHINE（指定目标平台）

```
/MACHINE:{ARM|EBC|X64|X86}
```

## <a name="remarks"></a>备注

/MACHINE 选项指定程序的目标平台。

通常，您不必指定 /MACHINE 选项。 LINK 从 .obj 文件中推断出计算机类型。 但是，在某些情况下，LINK 无法确定计算机类型并发出 [链接器工具错误 LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md)。 如果出现这种错误，请指定/MACHINE。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **高级** " 属性页。

1. 修改 " **目标计算机** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
