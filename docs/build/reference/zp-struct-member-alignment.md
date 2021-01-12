---
description: '了解详细信息：/Zp (结构成员对齐) '
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
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "98104773"
---
# <a name="zp-struct-member-alignment"></a>/Zp（结构成员对齐）

控制如何将结构的成员打包到内存中，以及如何为模块中的所有结构指定相同的封装。

## <a name="syntax"></a>语法

> **`/Zp`**[**`1`**|**`2`**|**`4`**|**`8`**|**`16`**]

## <a name="remarks"></a>备注

**`/ZpN`** 选项告诉编译器存储每个结构成员的位置。 编译器将成员存储在边界上第一个成员的边界上，该边界是成员类型的大小或 *N* 字节边界。

下表描述了可用的封装值：

|/Zp 参数|效果|
|-|-|
|1|将结构打包在1个字节的边界上。 与 `/Zp` 相同。|
|2|将结构打包到2个字节的边界上。|
|4|将结构打包在4个字节的边界上。|
|8|将结构打包到8字节边界 (x86、ARM 和 ARM64) 的默认值。|
|16| 为 x64)  (默认值的16字节边界包结构。|

不要使用此选项，除非有特定的对齐要求。

> [!WARNING]
> Windows SDK 中的 C/c + + 标头采用了 **`/Zp8`** 内部封装。 当包含 Windows SDK 标头时，请不要更改默认设置，方法是 **`/Zp`** 在命令行上使用或使用 `#pragma pack` 。 否则，应用程序可能会导致运行时出现内存损坏。

你还可以使用[ `pack` 杂注](../../preprocessor/pack.md)来控制结构打包。 有关对齐的详细信息，请参阅：

- [`align`](../../cpp/align-cpp.md)

- [`alignof` 操作员](../../cpp/alignof-operator.md)

- [`__unaligned`](../../cpp/unaligned.md)

- [`/ALIGN` (节对齐) ](align-section-alignment.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **代码生成**" 属性页。

1. 修改 **结构成员对齐** 属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md) \
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
