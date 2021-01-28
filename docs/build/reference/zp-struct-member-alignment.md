---
description: 详细了解：/Zp（结构成员对齐）
title: /Zp（结构成员对齐）
ms.date: 01/08/2021
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
ms.openlocfilehash: 8d29c442726aff9503a42378fce6a7b8b09526ed
ms.sourcegitcommit: 14d6ae0d527d05d153e26463d4cd5ada0f43e864
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "98104773"
---
# <a name="zp-struct-member-alignment"></a>/Zp（结构成员对齐）

控制如何将结构成员打包到内存中，并在模块中为所有结构指定同一包装。

## <a name="syntax"></a>语法

> **`/Zp`**[**`1`**|**`2`**|**`4`**|**`8`**|**`16`**]

## <a name="remarks"></a>备注

**`/ZpN`** 选项指示编译器存储每个结构成员的位置。 编译器在边界上的第一个后存储成员，这是以下项中较小的项：成员类型大小或 N 字节边界。

下表中描述了可用的包装值：

|/Zp 参数|效果|
|-|-|
|1|在 1 字节边界上打包结构。 与 `/Zp` 相同。|
|2|在 2 字节边界上打包结构。|
|4|在 4 字节边界上打包结构。|
|8|在 8 字节边界上打包结构（x86、ARM 和 ARM64 的默认设置）。|
|16| 在 16 字节边界上打包结构（x64 的默认设置）。|

如果没有特定的对齐要求，请不要使用此选项。

> [!WARNING]
> Windows SDK 中的 C/C++ 标头假设内部 `/Zp8` 包装。 当包含 Windows SDK 标头时，请不要通过在命令行上使用 `/Zp` 或使用 `#pragma pack` 更改设置的默认值。 否则，应用程序可能会导致运行时出现内存损坏。

还可以使用 [`pack` pragma](../../preprocessor/pack.md) 来控制结构打包。 有关对齐的详细信息，请参阅：

- [`align`](../../cpp/align-cpp.md)

- [`alignof` 运算符](../../cpp/alignof-operator.md)

- [`__unaligned`](../../cpp/unaligned.md)

- [`/ALIGN`（节对齐）](align-section-alignment.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择“配置属性” > “C/C++” > “代码生成”属性页面  。

1. 修改“结构成员对齐”属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>。

## <a name="see-also"></a>另请参阅

[MSVC 编译器选项](compiler-options.md) \
[MSVC 编译器命令行语法](compiler-command-line-syntax.md)
