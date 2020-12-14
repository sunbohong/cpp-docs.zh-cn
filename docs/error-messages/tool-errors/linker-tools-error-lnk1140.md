---
description: 了解详细信息：链接器工具错误 LNK1140
title: 链接器工具错误 LNK1140
ms.date: 11/04/2016
f1_keywords:
- LNK1140
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
ms.openlocfilehash: cde57e3594035aecc1cc3608d1329c5bc0752624
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281192"
---
# <a name="linker-tools-error-lnk1140"></a>链接器工具错误 LNK1140

程序数据库的模块太多;与/PDB： NONE 链接

项目包含4096个以上的模块。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>使用以下可能的解决方案进行修复

1. 使用 [/pdb： NONE](../../build/reference/pdb-use-program-database.md)进行重新链接。

1. 编译某些模块而不调试信息。

1. 减少模块的数量。
