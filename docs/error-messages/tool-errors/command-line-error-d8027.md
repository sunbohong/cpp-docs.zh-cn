---
description: 了解详细信息： Command-Line 错误 D8027
title: 命令行错误 D8027
ms.date: 11/04/2016
f1_keywords:
- D8027
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
ms.openlocfilehash: 80d0812571043249616108e99e763b105b527475
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115646"
---
# <a name="command-line-error-d8027"></a>命令行错误 D8027

无法执行 "component"

编译器无法运行给定的编译器组件或链接器。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 没有足够的内存来加载组件。 如果 NMAKE 调用了编译器，请在生成文件之外运行编译器。

1. 当前操作系统无法运行该组件。 请确保路径指向适用于你的操作系统的可执行文件。

1. 组件已损坏。 使用安装程序重新复制分发磁盘中的组件。

1. 未正确指定选项。 例如：

    ```
    cl /B1 file1.c
    ```
