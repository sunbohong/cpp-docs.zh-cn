---
description: 了解更多：资源编译器错误 RW1022
title: 资源编译器错误 RW1022
ms.date: 11/04/2016
f1_keywords:
- RW1022
helpviewer_keywords:
- RW1022
ms.assetid: 6747c8a9-9c9b-4422-b414-0645d22092d0
ms.openlocfilehash: 8c0ec5b4ca6f0d7ef910ded10736034858722b0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237226"
---
# <a name="resource-compiler-fatal-error-rw1022"></a>资源编译器错误 RW1022

**写入文件时出现 I/O 错误**

资源编译器无法写入文件。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 磁盘空间不足。 可用空间必须至少等于正在创建的可执行文件大小的两倍。

1. 卷为只读。

1. 坏扇区。

1. 共享冲突。
