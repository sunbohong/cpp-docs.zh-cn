---
description: 了解详细信息： NMAKE 错误 U1099
title: NMAKE 错误 U1099
ms.date: 11/04/2016
f1_keywords:
- U1099
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
ms.openlocfilehash: 8044010cf967e4fe27b2235968022023d66ae1c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345311"
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE 错误 U1099

堆栈溢出

正在处理的生成文件对于 NMAKE 中当前堆栈分配过于复杂。 NMAKE 分配了 0x3000 (12K) 。

若要增加 NMAKE 的堆栈分配，请使用更大的堆栈选项运行 [editbin/stack](../../build/reference/stack.md) 实用工具：

**editbin/STACK： reserve NMAKE.EXE**

其中， *reserve* 是大于 NMAKE 中当前堆栈分配的数字。
