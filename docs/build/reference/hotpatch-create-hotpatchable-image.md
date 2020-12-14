---
description: '了解详细信息：/hotpatch (创建可热修补映像) '
title: /hotpatch（创建可热修补的映像）
ms.date: 11/12/2018
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
ms.openlocfilehash: 2fc5fe629afcb1e721943b852c6f92351900ab7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199865"
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch（创建可热修补的映像）

准备映像以进行热修补。

## <a name="syntax"></a>语法

```
/hotpatch
```

## <a name="remarks"></a>备注

在编译中使用 **/hotpatch** 时，编译器可确保每个函数的第一个指令至少为两个字节，这是热修补所必需的。

若要完成创建映像可热修补的准备，请在使用 **/hotpatch** 进行编译后，使用 [/FUNCTIONPADMIN (创建可热修补图像)](functionpadmin-create-hotpatchable-image.md) 链接。 使用 cl.exe 的一次调用来编译和链接图像时， **/hotpatch** 表示 **/functionpadmin**。

由于指令在 ARM 体系结构上始终为两个字节或更大，并且由于 x64 编译始终被视为已指定 **/hotpatch** ，因此在为这些目标进行编译时，无需指定 **/hotpatch** ;但是，仍必须使用 **/functionpadmin** 进行链接，以便为其创建可热修补映像。 **/Hotpatch** 编译器选项仅影响 x86 编译。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 " **c/c + +** " 文件夹。

1. 选择 " **命令行** " 属性页。

1. 将编译器选项添加到 " **附加选项** " 框。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
