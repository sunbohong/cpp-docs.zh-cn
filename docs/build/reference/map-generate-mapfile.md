---
description: '了解详细信息：/MAP (生成映射) '
title: /MAP（生成映射文件）
ms.date: 11/04/2016
f1_keywords:
- /map
- VC.Project.VCLinkerTool.MapFileName
- VC.Project.VCLinkerTool.GenerateMapFile
helpviewer_keywords:
- mapfiles, creating linker
- generate mapfile linker option
- mapfile linker option
- mapfiles, information about program being linked
- MAP linker option
- -MAP linker option
- mapfiles, specifying file name
- /MAP linker option
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
ms.openlocfilehash: 28e3823099b4893dcf344a0b1aae99577d850821
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176426"
---
# <a name="map-generate-mapfile"></a>/MAP（生成映射文件）

```
/MAP[:filename]
```

## <a name="arguments"></a>参数

*filename*<br/>
用户指定的映射文件名。 它将替换默认名称。

## <a name="remarks"></a>备注

/MAP 选项告知链接器创建映射器。

默认情况下，链接器使用程序的基名称和扩展名 .map 命名映射器。 可选文件名允许您替代映射 *文件* 的默认名称。

映射文件是一个文本文件，其中包含有关要链接的程序的以下信息：

- 模块名称，它是文件的基名称

- 程序文件头中的时间戳不是从文件系统 () 

- 程序中的组列表，每个组的起始地址 (为 *节*：*Offset*) 、length、group name 和 class

- 公共符号列表，其中的每个地址 (为 *节*：*Offset*) 、符号名称、平面地址和 .obj 文件，其中定义了符号。

- 入口点 (为 *节*：*offset*) 

[/MAPINFO](mapinfo-include-information-in-mapfile.md)选项指定要包含在映射中的其他信息。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹。

1. 单击 " **调试** " 属性页。

1. 修改 " **生成映射文件** " 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参见 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A> 和 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
