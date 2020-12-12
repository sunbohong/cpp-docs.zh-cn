---
description: 了解详细信息：链接器工具错误 LNK1201
title: 链接器工具错误 LNK1201
ms.date: 11/04/2016
f1_keywords:
- LNK1201
helpviewer_keywords:
- LNK1201
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
ms.openlocfilehash: 2817e8f84d0a5d28aa012de5459eb7e09f383172
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341628"
---
# <a name="linker-tools-error-lnk1201"></a>链接器工具错误 LNK1201

写入程序数据库 "filename" 时出错;检查磁盘空间不足、路径无效或权限不足

对于输出文件 (PDB) ，LINK 无法写入程序数据库。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 文件已损坏。 删除 PDB 文件并重新链接。

1. 磁盘空间不足，无法写入文件。

1. 驱动器不可用，可能是由于网络问题导致的。

1. 调试器在您尝试链接的程序上处于活动状态。

1. 堆空间不足。  有关详细信息，请参阅 [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) 。
