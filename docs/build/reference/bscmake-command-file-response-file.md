---
description: '了解详细信息： BSCMAKE 命令文件 (响应文件) '
title: BSCMAKE 命令文件（响应文件）
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, response file
- BSCMAKE, command file
- response files, BSCMAKE
- command files, BSCMAKE
- response files
- command files
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
ms.openlocfilehash: 4bb321cd7aa705d7e33d0f539ab3e0aa2e3cb8bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187151"
---
# <a name="bscmake-command-file-response-file"></a>BSCMAKE 命令文件（响应文件）

> [!WARNING]
> 虽然安装 Visual Studio 时仍会安装 BSCMAKE，但 IDE 将不再使用它。 从 Visual Studio 2008 起，浏览信息和符号信息自动存储在解决方案文件夹的 SQL Server .sdf 文件中。

您可以在命令文件中提供部分或全部命令行输入。 使用以下语法指定命令文件：

```
BSCMAKE @filename
```

只允许使用一个命令文件。 您可以使用 *filename* 指定路径。 *Filename* 前面带有 at 符号 (**\@**) 。 BSCMAKE 不采用扩展。 可以在命令行中指定 *filename* 后面的其他 *sbrfiles* 。 命令文件是包含 BSCMAKE 输入的文本文件，其顺序与在命令行中指定的顺序相同。 用一个或多个空格、制表符或换行符分隔命令行参数。

以下命令使用命令文件调用 BSCMAKE：

```
BSCMAKE @prog1.txt
```

下面是一个示例命令文件：

```
/n /v /o main.bsc /El
/S (
toolbox.h
verdate.h c:\src\inc\screen.h
)
file1.sbr file2.sbr file3.sbr file4.sbr
```

## <a name="see-also"></a>请参阅

[BSCMAKE 参考](bscmake-reference.md)
