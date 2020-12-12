---
description: '了解详细信息：/FILEALIGN (对齐文件中的部分) '
title: /FILEALIGN（对齐文件中的部分）
ms.date: 10/23/2017
f1_keywords:
- /filealign
helpviewer_keywords:
- linker align sections
- /FILEALIGN linker option
- -FILEALIGN linker option
- FILEALIGN linker option
ms.assetid: c1017a35-8d71-4ad9-934b-a3e3ea037fa0
ms.openlocfilehash: a67cf682c8fe55b80b2253864e08919e08242f74
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192157"
---
# <a name="filealign-align-sections-in-files"></a>/FILEALIGN（对齐文件中的部分）

使用 **/FILEALIGN** 链接器选项，可以将写入输出文件的节的对齐方式指定为指定大小的倍数。

## <a name="syntax"></a>语法

> __/FILEALIGN：__*size*

### <a name="parameters"></a>parameters

*大小*<br/>
节对齐大小（以字节为单位），该大小必须是2的幂。

## <a name="remarks"></a>备注

**/FILEALIGN** 选项导致链接器将输出文件中的每个部分与 *大小* 值的倍数的边界对齐。 默认情况下，链接器不使用固定的对齐大小。

可以使用 **/FILEALIGN** 选项提高磁盘利用率，提高页面从磁盘的加载速度。 对于在较小的设备上运行的应用，或使下载更小，分区大小可能很小。 磁盘上的分区对齐不影响内存中的对齐方式。

使用 [DUMPBIN](dumpbin-reference.md) 可查看有关输出文件中各节的信息。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**链接器**" 文件夹中的 "**命令行**" 属性页。

1. 在 "**附加选项**" 框中键入选项名称 **/FILEALIGN：** 和大小。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
