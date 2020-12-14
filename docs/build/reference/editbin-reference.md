---
description: 了解详细信息： EDITBIN 引用
title: EDITBIN 参考
ms.date: 11/04/2016
f1_keywords:
- editbin
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
ms.openlocfilehash: ad211ab85ac00cd716b7c3b8e381a9a448ea04ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201022"
---
# <a name="editbin-reference"></a>EDITBIN 参考

Microsoft COFF 二进制文件编辑器 ( # A0) 修改 (COFF) 二进制文件的通用对象文件格式。 您可以使用 EDITBIN 来修改对象文件、可执行文件和动态链接库 (DLL) 。

> [!NOTE]
> 只能从 Visual Studio 命令提示符启动此工具。 不能从系统命令提示符或从文件资源管理器启动此工具。

EDITBIN 不可用于使用 [/gl](gl-whole-program-optimization.md) 编译器选项生成的文件。 对使用/GL 生成的二进制文件进行的任何修改都必须通过重新编译和链接来实现。

- [EDITBIN 命令行](editbin-command-line.md)

- [EDITBIN 选项](editbin-options.md)

## <a name="see-also"></a>请参阅

[其他 MSVC 生成工具](c-cpp-build-tools.md)
