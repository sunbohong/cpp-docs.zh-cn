---
description: 详细了解：编译器警告 (等级 2) C4056
title: 编译器警告 (等级 2) C4056
ms.date: 11/04/2016
f1_keywords:
- C4056
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
ms.openlocfilehash: 5d8b96e97197e43bf288476e310ddd842a90ec48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326539"
---
# <a name="compiler-warning-level-2-c4056"></a>编译器警告 (等级 2) C4056

浮点常量算术溢出

浮点常量算法生成的结果超出了允许的最大值。

此警告可能是由于在常量算法期间执行了编译器优化导致的。 如果关闭 ([/od](../../build/reference/od-disable-debug.md)) 的优化，则可以安全地忽略此警告。

下面的示例生成 C4056：

```cpp
// C4056.cpp
// compile with: /W2 /LD
#pragma warning (default : 4056)
float fp_val = 1.0e300 * 1.0e300;   // C4056
```
