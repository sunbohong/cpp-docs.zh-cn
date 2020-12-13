---
description: 了解更多： ML 非严重错误 A2008
title: ML 非致命错误 A2008
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2008
helpviewer_keywords:
- A2008
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
ms.openlocfilehash: 4482304de3238954a01a0242bd84712012d691f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129293"
---
# <a name="ml-nonfatal-error-a2008"></a>ML 非致命错误 A2008

**语法错误：**

当前位置的标记导致了语法错误。

可能发生了下列情况之一：

- 在指令中添加或省略了点前缀。

- 保留字 (如 **C** 或 **SIZE**) 用作标识符。

- 使用的指令不适用于当前处理器或协处理器选择。

- 比较运行时运算符 (如 `==`) 在条件程序集语句（而不是关系运算符 (，例如 [EQ](operator-eq.md)) ）中使用。

- 给定的指令或指令的操作数太少。

- 使用了过时的指令。

## <a name="see-also"></a>请参阅

[ML 错误消息](ml-error-messages.md)
