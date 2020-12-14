---
description: '了解详细信息：/RELEASE (设置校验和) '
title: /RELEASE（设置校验和）
ms.date: 11/04/2016
f1_keywords:
- /release
- VC.Project.VCLinkerTool.SetChecksum
helpviewer_keywords:
- -RELEASE linker option
- /RELEASE linker option
- checksum setting
- RELEASE linker option
ms.assetid: 93bcadf4-29ac-4824-914b-6997e3751d22
ms.openlocfilehash: ed1e55dffb02ace26e91e262bd3e9514f056196e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225318"
---
# <a name="release-set-the-checksum"></a>/RELEASE（设置校验和）

```
/RELEASE
```

## <a name="remarks"></a>备注

/RELEASE 选项在 .exe 文件的标头中设置校验和。

操作系统需要设备驱动程序的校验和。 为设备驱动程序的发行版本设置校验和，以确保与将来的操作系统兼容。

如果指定了 [/SUBSYSTEM： NATIVE](subsystem-specify-subsystem.md) 选项，则默认情况下将设置/RELEASE 选项。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **高级** " 属性页。

1. 修改 " **设置校验和** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
