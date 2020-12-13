---
description: 了解更多： ML 错误 A1010
title: ML 错误 A1010
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1010
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
ms.openlocfilehash: 4a00d9594c71c8a22942e869d109bf51176394c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129501"
---
# <a name="ml-fatal-error-a1010"></a>ML 错误 A1010

**不匹配的块嵌套：**

块开始没有匹配的结尾，或块结束没有匹配的开头。 可能涉及以下内容之一：

- 高级指令，如 [。如果](dot-if.md)为，则为 [。重复](dot-repeat.md)或 [。WHILE](dot-while.md)。

- 条件程序集指令，如 [IF](if-masm.md)、 [REPEAT](repeat.md)或 **WHILE**。

- 结构或联合定义。

- 过程定义。

- 分段定义。

- [POPCONTEXT](popcontext.md)指令。

- 条件程序集指令，例如 [ELSE](else-masm.md)、 [ELSEIF](elseif-masm.md)或 **ENDIF** ，无需匹配 [IF](if-masm.md)。

## <a name="see-also"></a>请参阅

[ML 错误消息](ml-error-messages.md)
