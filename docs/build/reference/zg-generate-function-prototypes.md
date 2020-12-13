---
description: '了解详细信息：/Zg (生成函数原型) '
title: /Zg（生成函数原型）
ms.date: 11/04/2016
f1_keywords:
- /zg
helpviewer_keywords:
- Zg compiler option [C++]
- /Zg compiler option [C++]
- function prototypes, generate function prototypes compiler option
- -Zg compiler option [C++]
- generate function prototypes compiler option
ms.assetid: c8df1b46-24ff-46f2-8356-e0a144b21dd2
ms.openlocfilehash: ee0bed48f15acae867d344a60a6d42f3b17c7e85
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178870"
---
# <a name="zg-generate-function-prototypes"></a>/Zg（生成函数原型）

删除。 为源文件中定义的每个函数创建函数原型，但不编译源文件。

## <a name="syntax"></a>语法

```
/Zg
```

## <a name="remarks"></a>备注

此编译器选项不再可用。 它在 Visual Studio 2015 中被删除。 此页面仍适用于旧版 Visual Studio 的用户。

函数原型包括函数返回类型和参数类型列表。 参数类型列表是根据函数的形参类型创建的。 将忽略源文件中已存在的任何函数原型。

原型列表将写入标准输出。 此列表可能有助于验证函数的实参和形参是否兼容。 可通过将标准输出重定向到文件以保存此列表。 然后，可使用 **#include** 将函数原型列表包括为源文件的一部分。 此操作将引发编译器执行参数类型检查。

如果使用 **/Zg** 选项，并且你的程序包含具有结构、枚举或联合类型（或指向这些类型的指针）的形参，则每个结构、枚举或联合类型的声明必须带有标记（名称）。 在以下示例中，标记名为 `MyStruct`。

```C
// Zg_compiler_option.c
// compile with: /Zg
typedef struct MyStruct { int i; } T2;
void f2(T2 * t) {}
```

Visual Studio 2005 中弃用了 **/Zg** 选项，已在 visual studio 2015 中将其删除。 MSVC 编译器已删除对较旧的 C 样式代码的支持。 有关弃用的编译器选项的列表，请参阅 [按类别列出的编译器选项](compiler-options-listed-by-category.md)中的不 **推荐使用和已删除编译器选项**。

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
