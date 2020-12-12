---
description: 了解更多：编译器选项
title: MSVC 编译器选项
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler
- x86 MSVC compiler
- ARM MSVC compiler
- compiler options, C++
- x64 MSVC compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
ms.openlocfilehash: a6b124fa5fce68844d53c1324da48c17ef5a9ccf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197018"
---
# <a name="compiler-options"></a>编译器选项

cl.exe 是一种工具，用于控制 Microsoft c + + (MSVC) C 和 c + + 编译器和链接器。 cl.exe 只能在支持 Windows Microsoft Visual Studio 的操作系统上运行。

> [!NOTE]
> 只能从 Visual Studio 开发人员命令提示启动此工具。 不能从系统命令提示符或从文件资源管理器启动此工具。 有关详细信息，请参阅[通过命令行使用 MSVC 工具集](../building-on-the-command-line.md)。

编译器生成常见的对象文件格式 (COFF) 对象 ( .obj) 文件。 链接器 () 文件或动态链接库 (Dll) 生成可执行文件或动态链接库。

请注意，所有编译器选项都区分大小写。 可以使用正斜杠 (`/`) 或短划线 (`-`) 来指定编译器选项。

若要编译但不链接，请使用 [/c](c-compile-without-linking.md) 选项。

## <a name="find-a-compiler-option"></a>查找编译器选项

若要查找特定编译器选项，请参阅以下列表之一：

- [按字母顺序列出的编译器选项](compiler-options-listed-alphabetically.md)

- [按类别列出的编译器选项](compiler-options-listed-by-category.md)

## <a name="specify-compiler-options"></a>指定编译器选项

每个编译器选项的主题讨论了如何在开发环境中设置它。 有关在开发环境之外指定选项的信息，请参阅：

- [MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)

- [CL 命令文件](cl-command-files.md)

- [CL 环境变量](cl-environment-variables.md)

## <a name="related-build-tools"></a>相关生成工具

[MSVC 链接器选项](linker-options.md) 还会影响程序的生成方式。

## <a name="see-also"></a>请参阅

[C/C++ 生成参考](c-cpp-building-reference.md)<br/>
[CL 调用链接器](cl-invokes-the-linker.md)
