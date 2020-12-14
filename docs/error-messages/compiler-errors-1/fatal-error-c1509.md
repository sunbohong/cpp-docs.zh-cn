---
description: 了解详细信息：严重错误 C1509
title: 错误 C1509
ms.date: 11/04/2016
f1_keywords:
- C1509
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
ms.openlocfilehash: dc2483ae96f599912b3ba6d1594257fec81ac251
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276343"
---
# <a name="fatal-error-c1509"></a>错误 C1509

编译器限制：函数 "function" 中有太多异常处理程序状态。 化简函数

代码超出了对异常处理程序状态的内部限制 (32768 状态) 。

最常见的原因是该函数包含用户定义的类变量和算术运算符的复杂表达式。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>使用以下可能的解决方案进行修复

1. 通过将常见子表达式分配给临时变量，简化表达式。

1. 将函数拆分为较小的函数。
