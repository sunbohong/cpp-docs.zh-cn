---
description: 了解详细信息： DUMPBIN 命令行
title: DUMPBIN 命令行
ms.date: 11/04/2016
helpviewer_keywords:
- DUMPBIN program, command line
ms.assetid: e6ad17d3-965d-41aa-9dfd-75bb073718d4
ms.openlocfilehash: 96b4216307201613c82a4671b9eb10bddab18e90
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192676"
---
# <a name="dumpbin-command-line"></a>DUMPBIN 命令行

若要运行 DUMPBIN，请使用以下语法：

```
DUMPBIN [options] files...
```

指定一个或多个二进制文件，以及控制信息所需的任何选项。 DUMPBIN 将信息显示到标准输出。 可以将其重定向到文件，也可以使用/OUT 选项指定输出文件的名称。

如果在未指定选项的情况下在文件上运行 DUMPBIN，则 DUMPBIN 将显示/SUMMARY 输出。

在 `dumpbin` 不使用任何其他命令行输入的情况下键入命令时，DUMPBIN 会显示汇总其选项的使用情况语句。

## <a name="see-also"></a>请参阅

[其他 MSVC 生成工具](c-cpp-build-tools.md)<br/>
[DUMPBIN 引用](dumpbin-reference.md)
