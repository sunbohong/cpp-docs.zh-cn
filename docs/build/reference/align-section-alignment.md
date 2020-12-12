---
description: '了解详细信息：/ALIGN (节对齐) '
title: /ALIGN（节对齐）
ms.date: 12/29/2017
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
ms.openlocfilehash: d8a9af473252a2eff8957c5d2b4c54c7f7c862aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187255"
---
# <a name="align-section-alignment"></a>/ALIGN（节对齐）

## <a name="syntax"></a>语法

> **/Align**[**：**_number_]

### <a name="arguments"></a>参数

*数字*<br/>
对齐值（以字节为单位）。

## <a name="remarks"></a>备注

**/Align** 选项指定程序的线性地址空间内每个部分的对齐方式。 *Number* 参数以字节为单位，必须是2的幂。 默认值为 4K (4096) 。 如果对齐方式产生的图像无效，链接器会发出警告。

除非您要编写一个应用程序（如设备驱动程序），否则不需要修改对齐方式。

可以使用 align 参数修改特定节与 [/SECTION](section-specify-section-attributes.md) 选项的对齐方式。

指定的对齐值不能小于最大的节对齐方式。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**  >  **链接器**  >  **命令行**" 属性页。

1. 在 " **附加选项** " 框中输入选项。 选择 **"确定" 或 "** **应用** " 以应用更改。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
