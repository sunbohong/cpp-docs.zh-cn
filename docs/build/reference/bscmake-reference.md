---
description: 了解详细信息： BSCMAKE 参考
title: BSCMAKE 参考
ms.date: 05/06/2019
helpviewer_keywords:
- BSCMAKE, reference
- Microsoft Browse Information Maintenance Utility
- browse windows
- browse information files (.bsc), building
- .bsc files, building
- bsc files, building
- BSCMAKE
ms.assetid: b97ad994-1355-4809-98db-6abc12c6fb13
ms.openlocfilehash: 11a90561e22b9fb3a39f022ba188e5c9d155e45e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179424"
---
# <a name="bscmake-reference"></a>BSCMAKE 参考

> [!WARNING]
> 虽然安装 Visual Studio 时仍会安装 BSCMAKE，但 IDE 将不再使用它。 从 Visual Studio 2008 起，浏览信息和符号信息自动存储在解决方案文件夹的 SQL Server .sdf 文件中。

Microsoft 浏览信息维护实用工具 (BSCMAKE.EXE) 从编译期间创建的 .sbr 文件生成浏览信息文件 (.bsc)。 某些第三方工具使用 .bsc 文件进行代码分析。

生成程序时，可以使用 BSCMAKE 生成浏览信息文件，以自动为你的程序创建浏览信息文件。 如果在 Visual Studio 开发环境中创建浏览信息文件，则无需知道如何运行 BSCMAKE。 但是，你可能需要阅读本主题以了解可用的选项。

如果在开发环境外部生成程序，则仍可以创建一个可在该环境中检查的自定义 .bsc。 对编译期间创建 .sbr 文件运行 BSCMAKE。

> [!NOTE]
> 只能在 Visual Studio 开发人员命令提示符下启动此工具。 不能从系统命令提示符或从文件资源管理器启动此工具。

本节包括下列主题：

- [生成浏览信息文件：概述](building-browse-information-files-overview.md)

- [生成 .bsc 文件](building-a-dot-bsc-file.md)

- [BSCMAKE 命令行](bscmake-command-line.md)

- [BSCMAKE 命令行](bscmake-command-file-response-file.md)

- [BSCMAKE 选项](bscmake-options.md)

- [BSCMAKE 退出代码](bscmake-exit-codes.md)

## <a name="see-also"></a>请参阅

[其他 MSVC 生成工具](c-cpp-build-tools.md)
