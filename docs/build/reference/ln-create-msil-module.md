---
description: '了解详细信息：/LN (创建 MSIL 模块) '
title: /LN（创建 MSIL 模块）
ms.date: 11/04/2016
f1_keywords:
- /LN
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
ms.openlocfilehash: 63b6f47fe6bef24341d3c19a6ad96ac3808e486e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190910"
---
# <a name="ln-create-msil-module"></a>/LN（创建 MSIL 模块）

指定不应将程序集清单插入输出文件中。

## <a name="syntax"></a>语法

```
/LN
```

## <a name="remarks"></a>备注

默认情况下， **/LN** 不会 (程序集清单插入到) 输出文件中。

当使用 **/LN** 时，还必须使用 [/Clr (公共语言运行时编译)](clr-common-language-runtime-compilation.md) 选项之一。

清单中不具有程序集元数据的托管程序称为 "模块"。 如果使用/c 进行编译 [ (编译但未链接)](c-compile-without-linking.md) 和 **/LN**，请在链接器阶段指定 [/NOASSEMBLY (创建 MSIL) 模块](noassembly-create-a-msil-module.md) 以创建输出文件。

如果希望采用基于组件的方法来生成程序集，则可能需要创建模块。  也就是说，您可以创作类型并将其编译到模块中。  然后，可以从一个或多个模块生成程序集。  有关从模块创建程序集的详细信息，请参阅 [.Netmodule 文件作为链接器输入](netmodule-files-as-linker-input.md) ，或 [Al.exe (程序集链接器) ](/dotnet/framework/tools/al-exe-assembly-linker)。

模块的默认文件扩展名为 .netmodule。

在 Visual Studio 2005 之前的版本中，使用 **/clr： noAssembly** 创建了一个模块。

MSVC 链接器接受. .netmodule 文件作为输入，并且链接器生成的输出文件将是程序集或 .netmodule，它对任何已输入到链接器的 netmodule 都没有运行时依赖关系。  有关详细信息，请参阅 [用作链接器输入的 .netmodule 文件](netmodule-files-as-linker-input.md)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

- 在链接器阶段指定 [/NOASSEMBLY (创建 MSIL 模块) ](noassembly-create-a-msil-module.md) 以创建输出文件。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 不能以编程方式更改此编译器选项。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
