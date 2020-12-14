---
description: '了解详细信息：/Fm (名称映射) '
title: /Fm（命名映射文件）
ms.date: 11/04/2016
f1_keywords:
- /fm
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
ms.openlocfilehash: 5c86a18ae9880a499997bcac2d8411859753d858
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200476"
---
# <a name="fm-name-mapfile"></a>/Fm（命名映射文件）

通知链接器生成一个映射文件，其中包含一系列段，这些段按它们在相应 .exe 文件或 DLL 中出现的顺序排列。

## <a name="syntax"></a>语法

```
/Fmpathname
```

## <a name="remarks"></a>备注

默认情况下，会为映射文件提供对应 C 或 c + + 源文件的基名称，其中包含。映射扩展。

指定 **/Fm** 的效果与) 链接器选项指定了 [/MAP (生成映射](map-generate-mapfile.md) 器的效果相同。

如果指定 [/c (编译但不链接)](c-compile-without-linking.md) 以取消链接，则 **/Fm** 不起作用。

映射中的全局符号通常具有一个或多个前导下划线，因为编译器会向变量名称中添加前导下划线。 映射中出现的许多全局符号由编译器和标准库在内部使用。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 点击“命令行”  属性页。

1. 在 **“附加选项”** 框中键入编译器选项。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[Output-File (/F) 选项](output-file-f-options.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)<br/>
[指定路径名](specifying-the-pathname.md)
