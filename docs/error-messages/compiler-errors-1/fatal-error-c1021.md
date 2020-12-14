---
description: 了解详细信息：严重错误 C1021
title: 错误 C1021
ms.date: 11/04/2016
f1_keywords:
- C1021
helpviewer_keywords:
- C1021
ms.assetid: e23171f4-ca6b-40c0-a913-a2edc6fa3766
ms.openlocfilehash: 74998b7b745ab2c0404ecea3392750b71cd40c6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316344"
---
# <a name="fatal-error-c1021"></a>错误 C1021

无效的预处理器命令“string”

`string` 不是有效的 [预处理器指令](../../preprocessor/preprocessor-directives.md)。 若要解决此错误，请使用对于 `string`有效预处理器名称。

下面的示例生成 C1021：

```cpp
// C1021.cpp
#BadPreProcName    // C1021 delete line
```
