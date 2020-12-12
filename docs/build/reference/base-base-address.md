---
description: '了解详细信息：/BASE (基址) '
title: /BASE（基址）
ms.date: 09/05/2018
f1_keywords:
- /base
- VC.Project.VCLinkerTool.BaseAddress
helpviewer_keywords:
- base addresses [C++]
- programs [C++], preventing relocation
- semicolon [C++], specifier
- -BASE linker option
- key address size
- environment variables [C++], LIB
- programs [C++], base address
- LIB environment variable
- BASE linker option
- DLLs [C++], linking
- /BASE linker option
- '@ symbol for base address'
- executable files [C++], base address
- at sign symbol for base address
ms.assetid: 00b9f6fe-0bd2-4772-a69c-7365eb199069
ms.openlocfilehash: 269911c7d9fce47be1b9755ddebf38170ea4e81c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182770"
---
# <a name="base-base-address"></a>/BASE（基址）

指定程序的基址。

## <a name="syntax"></a>语法

> **/Base：**{*address*[**，**<em>size</em>] | **\@**<em>filename</em>**，**<em>key</em>}

## <a name="remarks"></a>备注

> [!NOTE]
> 出于安全原因，Microsoft 建议你使用 [/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md) 选项，而不是为可执行文件指定基址。 这将生成可执行的映像，该映像可使用 Windows (ASLR) 功能在加载时随机变基。 默认情况下，/DYNAMICBASE 选项为 on。

/BASE 选项设置程序的基址，并覆盖 .exe 或 DLL 文件的默认位置。 .Exe 文件的默认基址为32位映像的0x400000 处或64位映像的0x140000000。 对于 DLL，默认基址为32位映像的0x10000000 或64位映像的0x180000000。 在不支持地址空间布局随机化 (ASLR) 的操作系统上，或者如果设置了/DYNAMICBASE： NO 选项，则操作系统将首先尝试加载位于其指定或默认基址的程序。 如果没有足够的空间，系统会重新定位程序。 若要防止重定位，请使用 [/FIXED](fixed-fixed-base-address.md) 选项。

如果 *地址* 不是64k 的倍数，则链接器会发出错误。 您可以选择指定程序的大小;如果程序无法适应您指定的大小，链接器会发出警告。

在命令行中指定基址的另一种方法是使用基址响应文件。 基址响应文件是一个文本文件，其中包含程序将使用的所有 Dll 的基址和可选大小，以及每个基址的唯一文本键。 若要使用响应文件指定基址，请使用 at 符号 (**\@**) 后跟响应文件的名称， *文件名*，后跟一个逗号，然后是要在文件中使用的基址的 *键值* 。 链接器将在指定的路径中查找 *文件名* ，如果未指定路径，则在 LIB 环境变量中指定的目录中查找。 *Filename* 中的每行都表示一个 DLL，并且具有以下语法：

> *key* *address* [*size*] **;** *comment*

*该键* 是字母数字字符的字符串，不区分大小写。 它通常是 DLL 的名称，但不需要。 *键* 后跟 C 语言、十六进制或十进制表示法中的基 *址* 和可选的最大 *大小*。 所有三个参数之间用空格或制表符分隔。 如果指定的 *大小* 小于程序所需的虚拟地址空间，则链接器会发出警告。 *注释* 由分号 (**;**) ，可以在同一行或单独的行上。 链接器将忽略从分号到行尾的所有文本。 此示例显示了此类文件的一部分：

```
main   0x00010000    0x08000000    ; for PROJECT.exe
one    0x28000000    0x00100000    ; for DLLONE.DLL
two    0x28100000    0x00300000    ; for DLLTWO.DLL
```

如果 DLLS.txt 包含这些行的文件，则以下示例命令将应用以下信息：

```
link dlltwo.obj /dll /base:@dlls.txt,two
```

设置基址的另一种方法是在 [名称](name-c-cpp.md)或 [库](library.md)语句中使用 *base* 参数。 /BASE 和 [/DLL](dll-build-a-dll.md) 选项一起与 **LIBRARY** 语句等效。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**  >  **链接器**  >  **高级** 属性" 页。

1. 修改 **基址** 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.BaseAddress%2A>。

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
