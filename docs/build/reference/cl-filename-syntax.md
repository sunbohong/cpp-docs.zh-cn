---
description: 了解详细信息： CL 文件名语法
title: CL 文件名语法
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, compiler filename
- paths, CL compiler filename syntax
- cl.exe compiler, filename syntax
- extensions, specifying to compiler
- file names [C++], CL compiler
- file names [C++]
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
ms.openlocfilehash: c7a657b54f69e2cdc0a126c55bb4102589a84290
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182435"
---
# <a name="cl-filename-syntax"></a>CL 文件名语法

CL 接受具有遵循 FAT、HPFS 或 NTFS 命名约定的名称的文件。 任何文件名均可以包含完整或部分路径。 完整路径包括驱动器名和一个或多个目录名。 CL 接受用反斜杠分隔的文件名 (\\) 或正斜杠 (/) 。 包含空格文件名必须用双引号字符引起来。 部分路径忽略 CL 假定为当前驱动器的驱动器名。 如果不指定路径，则 CL 假定该文件位于当前目录。

文件扩展名确定处理文件的方式。 已编译具有扩展名 .c、.cxx 或 .cpp 的 C 和 C++ 文件。 将其他文件（包括 .obj 文件、库 (.lib) 和模块定义 (.def) 文件）传递给链接器而无需处理。

## <a name="see-also"></a>请参阅

[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
