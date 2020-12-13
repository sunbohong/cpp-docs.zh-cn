---
description: 了解更多： ML 非严重错误 A2006
title: ML 非致命错误 A2006
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2006
helpviewer_keywords:
- A2006
ms.assetid: b8a8f096-95df-42b5-85ed-d2530560a84c
ms.openlocfilehash: c9057b600d9f9ed11f31009c3964aac028ffa1f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129410"
---
# <a name="ml-nonfatal-error-a2006"></a>ML 非致命错误 A2006

**未定义的符号：标识符**

尝试使用未定义的符号。

可能发生了下列情况之一：

- 未定义符号。

- 某个字段不是指定结构的成员。

- 未包含在包含文件中的符号。

- 在没有 [EXTERN](extern-masm.md) 或 [EXTERNDEF](externdef.md) 指令的情况下使用了外部符号。

- 符号名拼写错误。

- 在其范围之外引用了本地代码标签。

## <a name="see-also"></a>请参阅

[ML 错误消息](ml-error-messages.md)
