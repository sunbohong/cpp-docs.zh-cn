---
description: '了解详细信息：/GA (Optimize for Windows 应用程序) '
title: /GA（Windows 应用程序优化）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication
- /ga
helpviewer_keywords:
- /GA compiler option [C++]
- GA compiler option [C++]
- -GA compiler option [C++]
- Optimize for Windows compiler options
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
ms.openlocfilehash: f9d65dce26e80b585abc4d67e2eef55f10cb365b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191974"
---
# <a name="ga-optimize-for-windows-application"></a>/GA（Windows 应用程序优化）

提高了用于访问线程本地存储 (TLS) 变量的 .exe 文件的更高效的代码。

## <a name="syntax"></a>语法

```
/GA
```

## <a name="remarks"></a>备注

**/GA** 可以加速对在基于 Windows 的程序中使用 [__declspec (线程)](../../cpp/declspec.md) 声明的数据的访问。 如果设置了此选项，则假定 [__tls_index](/windows/win32/ProcThread/thread-local-storage) 宏为0。

对 DLL 使用 **/GA** 可能会导致代码生成错误。

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
