---
description: 了解更多：编译器错误 C3199
title: 编译器错误 C3199
ms.date: 11/04/2016
f1_keywords:
- C3199
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
ms.openlocfilehash: 598d21edbddc91d39edb9623dc59537d3e27bdf3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155470"
---
# <a name="compiler-error-c3199"></a>编译器错误 C3199

使用浮点 pragma 无效：在非精确模式下不支持异常

[Float_control](../../preprocessor/float-control.md)杂注用于指定 **/fp：精确** 的 [/fp](../../build/reference/fp-specify-floating-point-behavior.md)设置下的浮点异常模型。

下面的示例生成 C3199：

```cpp
// C3199.cpp
// compile with: /fp:fast
#pragma float_control(except, on)   // C3199
```
