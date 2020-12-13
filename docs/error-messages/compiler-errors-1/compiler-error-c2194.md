---
description: 了解更多：编译器错误 C2194
title: 编译器错误 C2194
ms.date: 11/04/2016
f1_keywords:
- C2194
helpviewer_keywords:
- C2194
ms.assetid: df6e631c-0062-4844-9088-4cc7a0ff879f
ms.openlocfilehash: fefdfbc434dce1347ff4a46a56040219f64feb47
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337638"
---
# <a name="compiler-error-c2194"></a>编译器错误 C2194

"identifier"：是一个文本段

`data_seg`杂注使用与一起使用的段名 `code_seg` 。

下面的示例生成 C2194：

```cpp
// C2194.cpp
// compile with: /c
#pragma code_seg("MYCODE")
#pragma data_seg("MYCODE")   // C2194
#pragma data_seg("MYCODE2")   // OK
```
