---
description: '了解详细信息：/FUNCTIONPADMIN (创建可热修补映像) '
title: /FUNCTIONPADMIN（创建可热修补的映像）
ms.date: 03/09/2018
f1_keywords:
- /functionpadmin
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
ms.openlocfilehash: f86adb2001adacf1b6c8a03a90b7452505841c08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192000"
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN（创建可热修补的映像）

准备映像以进行热修补。

## <a name="syntax"></a>语法

> **/FUNCTIONPADMIN**[**：**_space_]

### <a name="arguments"></a>参数

*空间*<br/>
要添加到每个函数开头的填充量（以字节为单位）。 在 x86 上，此值默认为5个字节，在 x64 上默认为6个字节。 在其他目标上，必须提供一个值。

## <a name="remarks"></a>备注

为了使链接器生成可热修补的图像，必须已使用/hotpatch 编译 .obj 文件 [ (创建可热修补映像) ](hotpatch-create-hotpatchable-image.md)。

当你使用 cl.exe 的单个调用来编译和链接图像时， **/hotpatch** 表示 **/functionpadmin**。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择“配置属性” > “链接器” > “命令行”属性页    。

1. 在 "**其他选项**" 中输入 **/FUNCTIONPADMIN** 选项。 选择“确定”以保存更改  。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
