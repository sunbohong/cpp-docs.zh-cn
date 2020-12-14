---
description: 了解详细信息：链接器工具错误 LNK1106
title: 链接器工具错误 LNK1106
ms.date: 11/04/2016
f1_keywords:
- LNK1106
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
ms.openlocfilehash: 85f353b6424cdd9ad12a99b29fec4f6119472cdb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281400"
---
# <a name="linker-tools-error-lnk1106"></a>链接器工具错误 LNK1106

文件无效或磁盘已满：无法查找到位置

此工具无法 `location` 在内存映射文件中读取或写入。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 磁盘已满。

   释放一些空间，并再次链接。

1. 尝试通过网络链接。

   某些网络不完全支持链接器使用的内存映射文件。 尝试链接本地磁盘。

1. 磁盘上的坏块。

   尽管操作系统和磁盘硬件应检测到这样的错误，但您可能希望运行磁盘检查程序。

1. 堆空间不足。

   有关详细信息，请参阅 [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) 。
