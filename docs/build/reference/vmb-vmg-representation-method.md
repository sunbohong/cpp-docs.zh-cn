---
description: '了解详细信息：/vmb、/vmg (表示法方法) '
title: /vmb、/vmg（表示方法）
ms.date: 11/04/2016
f1_keywords:
- /vmb
- /vmg
helpviewer_keywords:
- vmb compiler option [C++]
- -vmg compiler option [C++]
- vmg compiler option [C++]
- -vmb compiler option [C++]
- /vmb compiler option [C++]
- representation method compiler options [C++]
- /vmg compiler option [C++]
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
ms.openlocfilehash: 19d183ef8d1dd152043d7249d907c9d5b48de230
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254275"
---
# <a name="vmb-vmg-representation-method"></a>/vmb、/vmg（表示方法）

选择编译器用来表示指向类成员的指针的方法。

如果在声明指向类成员的指针之前始终定义类，请使用 **/vmb** 。

在定义类之前，使用 **/vmg** 声明指向类的成员的指针。 如果在两个不同的类中定义成员，则会出现这种需要。 对于这种相互引用的类，必须在定义类之前对其进行引用。

## <a name="syntax"></a>语法

```
/vmb
/vmg
```

## <a name="remarks"></a>备注

你还可以在代码中使用 [pointers_to_members](../../preprocessor/pointers-to-members.md) 或 [继承关键字](../../cpp/inheritance-keywords.md) 来指定指针表示形式。

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
