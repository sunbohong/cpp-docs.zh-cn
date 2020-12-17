---
description: 详细了解：带符号的按位运算
title: 带符号的按位运算
ms.date: 11/04/2016
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
ms.openlocfilehash: 98cca4d7450e0b65301ba3d2ad65f0cb3aca81ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292645"
---
# <a name="signed-bitwise-operations"></a>带符号的按位运算

**ANSI 3.3**：对带符号整数进行的按位运算的结果

对带符号整数进行的按位运算的工作方式与对无符号整数进行的按位运算的工作方式相同。 例如，`-16 & 99` 可用二进制格式表示

```
  11111111 11110000
& 00000000 01100011
  _________________
  00000000 01100000
```

按位“与”的结果为 96。

## <a name="see-also"></a>请参阅

[整数](../c-language/integers.md)
