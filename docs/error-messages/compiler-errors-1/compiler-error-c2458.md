---
description: 了解更多：编译器错误 C2458
title: 编译器错误 C2458
ms.date: 11/04/2016
f1_keywords:
- C2458
helpviewer_keywords:
- C2458
ms.assetid: ed21901f-1067-42f5-b275-19b480decf5c
ms.openlocfilehash: 7f705511c14da19b125868c1b34d907d6b5f220e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262849"
---
# <a name="compiler-error-c2458"></a>编译器错误 C2458

"identifier"：定义内的重定义

类、结构、联合或枚举在其自己的声明中重新定义。

下面的示例生成 C2458：

```cpp
// C2458.cpp
class C {
   enum i { C };   // C2458
};
```
