---
description: '了解详细信息：/STUB (MS-DOS 存根文件名) '
title: /STUB（MS-DOS 存根 (stub) 文件名）
ms.date: 11/04/2016
f1_keywords:
- /stub
- VC.Project.VCLinkerTool.DosStub
helpviewer_keywords:
- Win32 [C++], attaching MS-DOS stub program
- STUB linker option
- MS-DOS stub file name linker option
- /STUB linker option
- Windows API [C++], attaching MS-DOS stub program
- -STUB linker option
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
ms.openlocfilehash: 34f3cd71ce66cb6695a58707fd84de79f7a14b1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230297"
---
# <a name="stub-ms-dos-stub-file-name"></a>/STUB（MS-DOS 存根 (stub) 文件名）

```
/STUB:filename
```

## <a name="arguments"></a>参数

*filename*<br/>
MS-DOS 应用程序。

## <a name="remarks"></a>备注

/STUB 选项可将 MS-DOS 存根程序附加到 Win32 程序。

如果在 MS-DOS 中执行该文件，则会调用存根程序。 它通常会显示相应的消息;但是，任何有效的 MS-DOS 应用程序都可以是存根程序。

在命令行中的冒号 (： ) 之后指定存根程序的 *文件名* 。 如果文件不是可执行文件，则链接器将检查 *filename* 并发出错误消息。 程序必须是 .exe 文件;对于存根程序，.com 文件无效。

如果未使用此选项，则链接器会附加发出以下消息的默认存根（stub）程序：

```
This program cannot be run in MS-DOS mode.
```

构建虚拟设备驱动程序时， *filename* 允许用户指定包含 WINNT 中定义 (IMAGE_DOS_HEADER 结构的文件名。H) 用于 VXD，而不是默认标头。

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
