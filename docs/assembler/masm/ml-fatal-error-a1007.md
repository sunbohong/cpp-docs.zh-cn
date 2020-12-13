---
description: 了解更多： ML 错误 A1007
title: ML 错误 A1007
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1007
helpviewer_keywords:
- A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
ms.openlocfilehash: c26d5de1c1b44fb37d4a95f51b2cb9480d2ba664
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129540"
---
# <a name="ml-fatal-error-a1007"></a>ML 错误 A1007

**嵌套级别太深**

汇编程序已达到其嵌套限制。 限制为20个级别，但在其他情况下除外。

下面其中一个内容嵌套太深：

- 高级指令，如 [。如果](dot-if.md)为，则为 [。重复](dot-repeat.md)或 [。WHILE](dot-while.md)。

- 结构定义。

- 条件程序集指令。

- 过程定义。

- [PUSHCONTEXT](pushcontext.md)指令 (的限制为 10) 。

- 分段定义。

- 包含文件。

- 宏。

## <a name="see-also"></a>请参阅

[ML 错误消息](ml-error-messages.md)
