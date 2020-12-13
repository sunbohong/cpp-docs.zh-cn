---
description: 了解更多： ML 非严重错误 A2085
title: ML 非致命错误 A2085
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2085
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
ms.openlocfilehash: 3a2cd89b373f761beb3fc0de01a1bea3ec7bf82e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97128540"
---
# <a name="ml-nonfatal-error-a2085"></a>ML 非致命错误 A2085

**当前 CPU 模式下未接受的指令或寄存器**

尝试使用的指令、寄存器或关键字对于当前处理器模式无效。

例如，32位寄存器需要 [386](dot-386.md) 或更高版本。 控制寄存器（如 CR0）需要特权模式 [。 .386p](dot-386p.md) 或更高版本。 还将为需要的 **NEAR32**、 **FAR32** 和 **平面** 关键字生成此错误。**386** 或更高版本。

## <a name="see-also"></a>请参阅

[ML 错误消息](ml-error-messages.md)
