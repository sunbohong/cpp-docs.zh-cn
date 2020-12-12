---
description: '了解有关以下方面的详细信息：/GF (消除重复的字符串) '
title: /GF（消除重复的字符串）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.StringPooling
- VC.Project.VCCLWCECompilerTool.StringPooling
- /gf
helpviewer_keywords:
- duplicate strings
- Eliminate Duplicate Strings compiler option [C++]
- pooling strings compiler option [C++]
- -GF compiler option [C++]
- /GF compiler option [C++]
- GF compiler option [C++]
- strings [C++], pooling
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
ms.openlocfilehash: 65c8cca610b9e01cf49939c2074a698b00c6e338
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191935"
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF（消除重复的字符串）

允许编译器在执行过程中在程序映像和内存中创建相同字符串的单个副本。 这是一种可创建较小程序的名为 *字符串池* 的优化。

## <a name="syntax"></a>语法

```
/GF
```

## <a name="remarks"></a>备注

如果使用 **/gf**，则操作系统不会交换内存的字符串部分，并且可以从映像文件中读取字符串。

**/Gf** 将字符串汇集为只读。 如果尝试在 **/gf** 下修改字符串，则会出现应用程序错误。

字符串池允许将多个指向多个缓冲区的指针作为多个指向单个缓冲区的指针。 在下面的代码中， `s` 和 `t` 是用同一字符串初始化的。 字符串池使它们指向相同的内存：

```
char *s = "This is a character buffer";
char *t = "This is a character buffer";
```

> [!NOTE]
> [/Zi](z7-zi-zi-debug-information-format.md)选项用于 "编辑并继续"，会自动设置 **/gf** 选项。

> [!NOTE]
> **/Gf** 编译器选项为每个唯一字符串创建一个可寻址部分。 默认情况下，对象文件最多可以包含65536个可寻址部分。 如果程序包含65536个以上的字符串，请使用 [/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md) 编译器选项来创建更多部分。

当使用 [/O1](o1-o2-minimize-size-maximize-speed.md)或 [/O2](o1-o2-minimize-size-maximize-speed.md)时， **/gf** 有效。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 单击 " **代码生成** " 属性页。

1. 修改 " **启用字符串池** " 属性。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
