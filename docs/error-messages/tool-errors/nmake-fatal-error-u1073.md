---
description: 了解详细信息： NMAKE 错误 U1073
title: NMAKE 错误 U1073
ms.date: 11/04/2016
f1_keywords:
- U1073
helpviewer_keywords:
- U1073
ms.assetid: d46bf2dd-400a-4802-9db2-f832e1c97f02
ms.openlocfilehash: bd622f37720cf5e992a1d82ea97ca1ff50344c0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345441"
---
# <a name="nmake-fatal-error-u1073"></a>NMAKE 错误 U1073

不知道如何建立 "targetname"

指定的目标不存在，并且没有要执行的命令或要应用的推理规则。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>使用以下可能的解决方案进行修复

1. 检查目标名称的拼写。

1. 如果 *targetname* 为伪目标，则将其指定为另一个描述块中的目标。

1. 如果 *targetname* 是宏调用，请确保它不会扩展为空字符串。
