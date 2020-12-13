---
description: 了解更多： ML 非严重错误 A2031
title: ML 非致命错误 A2031
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2031
helpviewer_keywords:
- A2031
ms.assetid: d5b11f58-4a00-42be-9062-8fa8728e6306
ms.openlocfilehash: 8c92b4e3439a4e660c7c128e52bcadc668778189
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129215"
---
# <a name="ml-nonfatal-error-a2031"></a>ML 非致命错误 A2031

**必须是索引或基寄存器**

尝试使用的寄存器不是内存表达式中的基寄存器或索引寄存器。

例如，以下表达式将导致此错误：

```asm
[ax]
[bl]
```

## <a name="see-also"></a>请参阅

[ML 错误消息](ml-error-messages.md)
