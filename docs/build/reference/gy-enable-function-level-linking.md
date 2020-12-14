---
description: '了解有关以下内容的详细信息：/Gy (启用 Function-Level 链接) '
title: /Gy（启用函数级链接）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
ms.openlocfilehash: 3c4136b25001f7f6d6729b9c6089995d1bcd71bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200125"
---
# <a name="gy-enable-function-level-linking"></a>/Gy（启用函数级链接）

允许编译器以打包函数 (COMDAT) 形式对各个函数进行打包。

## <a name="syntax"></a>语法

```
/Gy[-]
```

## <a name="remarks"></a>备注

链接器要求将函数作为 Comdat 单独打包，以排除或排序 DLL 或 .exe 文件中的单个函数。

您可以使用链接器选项 [/opt (优化) ](opt-optimizations.md) 从 .exe 文件中排除未引用的打包函数。

您可以使用链接器选项 [/order (按顺序放置函数) ](order-put-functions-in-order.md) 在 .exe 文件中以指定顺序包含打包函数。

如果内联函数实例化为调用 (（例如，内联为 off 或) 函数地址），则这些函数将始终打包。 此外，类声明中定义的 c + + 成员函数会自动打包;其他函数不是，并且需要选择此选项以将其编译为打包函数。

> [!NOTE]
> [/Zi](z7-zi-zi-debug-information-format.md)选项用于 "编辑并继续"，会自动设置 **/gy** 选项。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 单击 " **代码生成** " 属性页。

1. 修改 " **启用 Function-Level 链接** " 属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
