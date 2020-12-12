---
description: 了解详细信息：链接输入文件
title: LINK 输入文件
ms.date: 11/04/2016
helpviewer_keywords:
- files [C++], LINK
- module definition files
- resources [C++], linker files
- LINK tool [C++], input files
- module definition files, linker files
- input files [C++], LINK
- linker [C++], input files
- import libraries [C++], linker files
- command input to linker files [C++]
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
ms.openlocfilehash: 3bf25d36ab61b35dfe3d1551e9f85e8c2f26862b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199501"
---
# <a name="link-input-files"></a>LINK 输入文件

为链接器提供包含对象、导入和标准库、资源、模块定义和命令输入的文件。 LINK 不使用文件扩展名对文件内容进行假设。 相反，LINK 检查每个输入文件以确定文件的类型。

命令行上的对象文件将按照它们在命令行上出现的顺序进行处理。 还将在命令行顺序中搜索库，但有以下注意事项：在库中引入对象文件时，将首先在该库中搜索未解析的符号，然后从命令行和/DEFAULTLIB 中搜索以下库 [ (指定默认库) ](defaultlib-specify-default-library.md) 指令，然后将其指定到命令行开始处的任何库。

> [!NOTE]
> 链接不再接受分号 (或任何其他字符) 作为响应文件和顺序文件中注释的开头。 分号仅在模块定义文件 () 中被识别为注释的开头。

LINK 使用以下类型的输入文件：

- [.obj 文件](dot-obj-files-as-linker-input.md)

- [.netmodule 文件](netmodule-files-as-linker-input.md)

- [.lib 文件](dot-lib-files-as-linker-input.md)

- [.exp 文件](dot-exp-files-as-linker-input.md)

- [.def 文件](dot-def-files-as-linker-input.md)

- [.pdb 文件](dot-pdb-files-as-linker-input.md)

- [res 文件](dot-res-files-as-linker-input.md)

- [.exe 文件](dot-exe-files-as-linker-input.md)

- [.txt 文件](dot-txt-files-as-linker-input.md)

- [.ilk 文件](dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
