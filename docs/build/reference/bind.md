---
description: 了解详细信息：/BIND
title: /BIND
ms.date: 11/04/2016
f1_keywords:
- /bind
helpviewer_keywords:
- -BIND editbin option
- entry points, addresses
- BIND editbin option
- entry points
- /BIND editbin option
- import address table
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
ms.openlocfilehash: 87ea0265555991fca019760feec4395692c074ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187138"
---
# <a name="bind"></a>/BIND

```
/BIND[:PATH=path]
```

## <a name="remarks"></a>备注

此选项设置可执行文件或 DLL 的导入地址表中的入口点地址。 使用此选项可减少程序的加载时间。

在 EDITBIN 命令行上的 *files* 参数中指定程序的可执行文件和 dll。 /BIND 的可选 *路径* 自变量指定指定文件使用的 dll 的位置。 使用分号 (**;**) 分隔多个目录。 如果未指定 *路径* ，EDITBIN 将搜索 path 环境变量中指定的目录。 如果指定 *path* ，EDITBIN 将忽略 path 变量。

默认情况下，程序加载程序在加载程序时设置入口点的地址。 此过程所需的时间会有所不同，具体取决于 Dll 的数量和程序中引用的入口点的数量。 如果已使用/BIND 修改了某个程序，并且可执行文件及其 Dll 的基址与已加载的 Dll 不冲突，则操作系统不需要设置这些地址。 在文件不正确的情况下，操作系统会重新定位该程序的 Dll 并重新计算入口点地址，这将添加到程序的加载时间。

## <a name="see-also"></a>请参阅

[EDITBIN 选项](editbin-options.md)
