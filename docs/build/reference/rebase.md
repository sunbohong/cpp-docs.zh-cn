---
description: 了解详细信息：/REBASE
title: /REBASE
ms.date: 11/04/2016
f1_keywords:
- /rebase
helpviewer_keywords:
- base addresses [C++]
- -REBASE editbin option
- REBASE editbin option
- DLLs [C++], linking
- executable files [C++], base address
- /REBASE editbin option [C++]
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
ms.openlocfilehash: 6cbbf0a21bd9306167fb165b63c22e810518e161
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225331"
---
# <a name="rebase"></a>/REBASE

```
/REBASE[:modifiers]
```

## <a name="remarks"></a>备注

此选项设置指定文件的基址。 EDITBIN 根据每个文件的大小舍入到最接近的 64 KB，在一个连续的地址空间中分配新的基址。 有关基址的详细信息，请参阅 [基址](base-base-address.md) (/base) 链接器选项。

按照它们的基于顺序在 EDITBIN 命令行上的 *files* 参数中指定程序的可执行文件和 dll。 您可以选择指定一个或多个 *修饰符*，每个修饰符由逗号 **分隔 ()** ：

|修饰符|操作|
|--------------|------------|
|**基 =**<em>地址</em>|提供用于向文件重新分配基址的开始地址。 以十进制或 C 语言表示法指定 *地址* 。 如果未指定 BASE，则默认起始基址为0x400000 处。 如果使用 DOWN，则必须指定 BASE， *地址* 设置基址范围的结束。|
|**BASEFILE**|创建一个名为 COFFBASE.TXT 的文件，该文件是链接的/BASE 选项所需格式的文本文件。|
|**DOWN**|告诉 EDITBIN 从结束地址向下重新分配基址。 文件按指定顺序重新分配，第一个文件位于地址范围末尾下的最高可能地址中。 必须将 BASE 与 DOWN 一起使用，以确保有足够的地址空间来基于文件。 若要确定指定文件所需的地址空间，请对文件运行包含/REBASE 的 EDITBIN，并将 64 KB 添加到显示的总大小。|

## <a name="see-also"></a>请参阅

[EDITBIN 选项](editbin-options.md)
