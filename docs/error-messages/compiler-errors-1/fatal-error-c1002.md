---
description: 了解详细信息：严重错误 C1002
title: 错误 C1002
ms.date: 11/04/2016
f1_keywords:
- C1002
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
ms.openlocfilehash: edd4ffbd6ce4c8a7f70640619d8dc52775dd0195
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262706"
---
# <a name="fatal-error-c1002"></a>错误 C1002

在第 2 遍中编译器的堆空间不足

编译器在第二次传递过程中用尽了动态内存空间，这可能是由于符号或复杂表达式太多而导致的。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>使用以下可能的解决方案进行修复

1. 将源文件分为多个较小的文件。

1. 将表达式分解为更小的子表达式。

1. 删除消耗内存的其他程序或驱动程序。
