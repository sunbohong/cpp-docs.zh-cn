---
description: 了解更多： ML 错误 A1011
title: ML 错误 A1011
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1011
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
ms.openlocfilehash: 294ca2cbf512948514317589628969a3e63e71af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129488"
---
# <a name="ml-fatal-error-a1011"></a>ML 错误 A1011

**指令必须在控制块中**

组装器找到了不需要的高级指令。 找到以下指令之一：

- [.否则](dot-else.md) ，则为 [。如果](dot-if.md)

- [.ENDIF](dot-endif.md) [，无。如果](dot-if.md)

- [..ENDW](dot-endw.md) （不含） [。WHILE](dot-while.md)

- [..UNTILCXZ](dot-untilcxz.md) （不含） [。重复](dot-repeat.md)

- [.](dot-continue.md) 不继续 [。WHILE](dot-while.md) 或 [。重复](dot-repeat.md)

- [.](dot-break.md) 不带 [的分行符。WHILE](dot-while.md) 或 [。重复](dot-repeat.md)

- [.其他](dot-else.md)`.ELSE`

## <a name="see-also"></a>请参阅

[ML 错误消息](ml-error-messages.md)
