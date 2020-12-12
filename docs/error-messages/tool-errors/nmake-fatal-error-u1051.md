---
description: 了解详细信息： NMAKE 错误 U1051
title: NMAKE 错误 U1051
ms.date: 11/04/2016
f1_keywords:
- U1051
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
ms.openlocfilehash: c7d465eaf34adb69e41f523006fb0740eea722ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272105"
---
# <a name="nmake-fatal-error-u1051"></a>NMAKE 错误 U1051

内存不足

由于 makefile 太大或太复杂，NMAKE 内存用尽，包括虚拟内存。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>使用以下可能的解决方案进行修复

1. 在磁盘上释放一些空间。

1. 增加 Windows NT 页面文件或 Windows 交换文件的大小。

1. 如果只使用部分生成文件，请将生成文件分成单独的文件或使用 **！如果** 预处理指令限制 NMAKE 必须处理的量，则为。 **！IF** 指令包括 **！如果**、 `!IFDEF` 、 **！IFNDEF**、 **！否则，IF**， **！ELSE** `IFDEF` 和 **！ELSE** `IFNDEF` 。
