---
description: 了解更多： ML 非严重错误 A2050
title: ML 非致命错误 A2050
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2050
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
ms.openlocfilehash: 9ae38353d3c2e2a2e25e3e5c4a87e3b3b6888781
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97128994"
---
# <a name="ml-nonfatal-error-a2050"></a>ML 非致命错误 A2050

**不允许使用 real 或 BCD 号**

浮点型 (实际) 数字或二进制编码的十进制数 (BCD) 常量被用作数据初始值设定项。

出现下列情况之一：

- 表达式中使用了实数或 BCD。

- 实数用于初始化 [DWORD](dword.md)、 [QWORD](qword.md)或 [TBYTE](tbyte.md)以外的指令。

- BCD 用于初始化以外的指令 `TBYTE` 。

## <a name="see-also"></a>请参阅

[ML 错误消息](ml-error-messages.md)
