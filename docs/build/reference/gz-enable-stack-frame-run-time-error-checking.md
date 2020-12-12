---
description: '了解详细信息：/GZ (启用堆栈帧 Run-Time 错误检查) '
title: /GZ（启用堆栈帧运行时错误检查）
ms.date: 11/04/2016
f1_keywords:
- /gz
helpviewer_keywords:
- -GZ compiler option [C++]
- release-build errors
- /GZ compiler option [C++]
- GZ compiler option [C++]
- debug builds, catch release-build errors
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
ms.openlocfilehash: 0b0936037c265bf57413c458ffc0a831184cb074
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191688"
---
# <a name="gz-enable-stack-frame-run-time-error-checking"></a>/GZ（启用堆栈帧运行时错误检查）

执行与 [/rtc (运行时错误检查) ](rtc-run-time-error-checks.md) 选项相同的操作。 已弃用。

## <a name="syntax"></a>语法

```
/GZ
```

## <a name="remarks"></a>备注

**/GZ** 仅适用于 nonoptimized ([/od (禁用 (调试) # B4](od-disable-debug.md)) 生成。

**/GZ** 已弃用，因为 Visual Studio 2005;改用 [/rtc (运行时错误检查)](rtc-run-time-error-checks.md) 。 有关弃用的编译器选项的列表，请参阅 [按类别列出的编译器选项](compiler-options-listed-by-category.md)中的不 **推荐使用和已删除编译器选项**。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 点击“命令行”  属性页。

1. 在 **“附加选项”** 框中键入编译器选项。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
