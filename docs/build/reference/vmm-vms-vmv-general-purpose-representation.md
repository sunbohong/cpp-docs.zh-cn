---
description: '了解详细信息：/vmm、/vms、/vmv (常规用途表示形式) '
title: '/vmm，-vm，-vmv (常规用途表示形式) '
ms.date: 11/04/2016
f1_keywords:
- /vms
- /vmm
- /vmv
helpviewer_keywords:
- Virtual Inheritance compiler option
- general purpose representation compiler options
- vms compiler option [C++]
- vmm compiler option [C++]
- /vmm compiler option [C++]
- -vmm compiler option [C++]
- -vms compiler option [C++]
- /vms compiler option [C++]
- vmv compiler option [C++]
- /vmv compiler option [C++]
- Single Inheritance compiler option
- -vmv compiler option [C++]
ms.assetid: 0fcd7ae0-3031-4c62-a2a8-e154c8685dae
ms.openlocfilehash: 8c5761a2f51ec9860a4afeb7d4aacbf7f882b3f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257220"
---
# <a name="vmm-vms-vmv-general-purpose-representation"></a>/vmm、/vms、/vmv（通用表示形式）

当 [/vmb、/vmg (表示方法) ](vmb-vmg-representation-method.md) 被选作 [表示方法](vmb-vmg-representation-method.md)时使用。 这些选项指示尚未遇到的类定义的继承模型。

## <a name="syntax"></a>语法

```
/vmm
/vms
/vmv
```

## <a name="remarks"></a>备注

下表描述了这些选项。

|选项|描述|
|------------|-----------------|
|**/vmm**|指定指向类成员的指针的最常见表示形式，该指针使用多个继承。<br /><br /> **Multiple_inheritance** [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md)对应的 [继承关键字](../../cpp/inheritance-keywords.md)和参数。<br /><br /> 此表示形式大于单次继承所需的表示形式。<br /><br /> 如果为其声明指向成员的指针的类定义的继承模型为虚，则编译器将生成错误。|
|**/vms**|指定指向类的成员的指针的最常见表示形式，该指针使用 "无继承" 或 "单一继承"。<br /><br /> **Single_inheritance** [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md)对应的 [继承关键字](../../cpp/inheritance-keywords.md)和参数。<br /><br /> 这是指向类的成员的指针的可能的最小表示形式。<br /><br /> 如果为其声明指向成员的指针的类定义的继承模型为多或虚拟，则编译器将生成错误。|
|**/vmv**|指定指向类成员的指针的最常见表示形式是使用虚拟继承的类型。 它永远不会导致错误，而是默认值。<br /><br /> **Virtual_inheritance** [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md)对应的 [继承关键字](../../cpp/inheritance-keywords.md)和参数。<br /><br /> 此选项需要更大的指针和其他代码来解释指针，而不是其他选项。|

当你指定这些继承模型选项之一时，该模型将用于指向类成员的所有指针，而不考虑它们的继承类型或是否在类之前或之后声明指针。 因此，如果始终使用单一继承类，可以通过使用 **/vms** 进行编译来减小代码大小;但是，如果你想要使用最常见的情况 (以最大数据表示形式的代价) ，请使用 **/vmv** 进行编译。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击 **“C/C++”** 文件夹。

1. 点击“命令行”  属性页。

1. 在 **“附加选项”** 框中键入编译器选项。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>请参阅

[/vmb，/vmg (表示法方法) ](vmb-vmg-representation-method.md)<br/>
[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
