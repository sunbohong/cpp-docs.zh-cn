---
description: '了解详细信息：/WINMDFILE (指定 winmd 文件) '
title: /WINMDFILE（指定 winmd 文件）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
ms.openlocfilehash: fd10768c494bbedfbe650e0f0e3e72e8a062cdc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259014"
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE（指定 winmd 文件）

指定由 [/WINMD](winmd-generate-windows-metadata.md) 链接器选项生成的 Windows 运行时元数据 ( winmd) 输出文件的文件名。

```
/WINMDFILE:filename
```

## <a name="remarks"></a>备注

使用 `filename` 中指定的值重写默认的 .winmd 文件名 (`binaryname`.winmd)。 请注意，不会将 "winmd" 追加到 `filename` 。  如果在 **/WINMDFILE** 命令行上列出了多个值，则将优先使用最后一个值。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 " **链接器** " 文件夹。

1. 选择 " **Windows 元数据** " 属性页。

1. 在 " **Windows 元数据文件** " 框中，输入文件位置。

## <a name="see-also"></a>请参阅

[/WINMD (生成 Windows 元数据) ](winmd-generate-windows-metadata.md)<br/>
[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
