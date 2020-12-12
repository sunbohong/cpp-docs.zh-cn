---
description: 了解详细信息： NMAKE 警告 U4010
title: NMAKE 警告 U4010
ms.date: 11/04/2016
f1_keywords:
- U4010
helpviewer_keywords:
- U4010
ms.assetid: 99d8eb9a-ae31-40d1-b8c5-8c66732127d3
ms.openlocfilehash: d0c72044576ebf3441fdec7980c933edec671097
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334793"
---
# <a name="nmake-warning-u4010"></a>NMAKE 警告 U4010

"target"：生成失败;已指定/k，正在继续 .。。

给定目标的命令块中的命令返回非零退出代码。 /K 选项告诉 NMAKE 继续处理生成的无关部分，并在 NMAKE 会话结束时发出退出代码1。

如果给定的目标是本身，它是另一个目标的依赖项，则 NMAKE 在此警告之后发出警告 [U4011](../../error-messages/tool-errors/nmake-warning-u4011.md) 。
