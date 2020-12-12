---
description: 了解详细信息： BSCMAKE Warning BK4502
title: BSCMAKE 警告 BK4502
ms.date: 11/04/2016
f1_keywords:
- BK4502
helpviewer_keywords:
- BK4502
ms.assetid: ee412ec8-df03-4cdb-91ee-5d609ded8691
ms.openlocfilehash: 97fb7745353a92704fb624a2782a91ea63dc532a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237876"
---
# <a name="bscmake-warning-bk4502"></a>BSCMAKE 警告 BK4502

截断.不在文件名中的 .SBR 文件 "filename"

在更新过程中未指定最初不属于 .bsc 文件的零长度 .sbr 文件。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 指定的文件名不正确。

1. 文件已删除。  (错误 [BK1513](../../error-messages/tool-errors/bscmake-error-bk1513.md) 结果。 ) 

1. 文件已损坏，要求 BSCMAKE 执行完整生成。
