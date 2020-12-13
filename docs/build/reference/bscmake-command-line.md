---
description: 了解详细信息： BSCMAKE 命令行
title: BSCMAKE 命令行
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, command line
ms.assetid: 8006e8cf-8bfe-4c23-868a-b0a25e6bbf0f
ms.openlocfilehash: a0d6cb81fb207c30cd89fbfe3a988380a865a399
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182653"
---
# <a name="bscmake-command-line"></a>BSCMAKE 命令行

> [!WARNING]
> 虽然安装 Visual Studio 时仍会安装 BSCMAKE，但 IDE 将不再使用它。 从 Visual Studio 2008 起，浏览信息和符号信息自动存储在解决方案文件夹的 SQL Server .sdf 文件中。

若要运行 BSCMAKE，请使用以下命令行语法：

```
BSCMAKE [options] sbrfiles
```

选项只能出现在 `options` 命令行上的字段中。

*Sbrfiles* 字段指定一个或多个由编译器或组装器创建的 .sbr 文件。 用空格或制表符分隔 .sbr 文件的名称。 必须指定扩展;没有默认值。 您可以使用文件名指定路径，并且可以使用操作系统通配符 (\* 和？ ) 。

在增量生成过程中，可以指定不属于原始生成的新 .sbr 文件。 如果希望所有贡献保留在浏览信息文件中，则必须指定所有 .sbr 文件 (包含最初用于创建 .bsc 文件) 的截断文件。 如果省略 .sbr 文件，则会删除该文件对浏览信息文件的贡献。

不要为完整生成指定截断的 .sbr 文件。 完全生成需要来自所有指定 .sbr 文件的发布。 在执行完整生成之前，请重新编译项目并为每个空文件创建新的 .sbr 文件。

以下命令运行 BSCMAKE，以从三个 .sbr 文件生成一个名为 ".bsc" 的文件：

```
BSCMAKE main.sbr file1.sbr file2.sbr
```

有关相关信息，请参阅 [Bscmake 命令文件](bscmake-command-file-response-file.md) 和 [bscmake 选项](bscmake-options.md)。

## <a name="see-also"></a>请参阅

[BSCMAKE 参考](bscmake-reference.md)
