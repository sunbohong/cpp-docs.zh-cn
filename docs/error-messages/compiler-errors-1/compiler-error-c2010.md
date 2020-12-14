---
description: 了解更多：编译器错误 C2010
title: 编译器错误 C2010
ms.date: 11/04/2016
f1_keywords:
- C2010
helpviewer_keywords:
- C2010
ms.assetid: 5795ed1d-e206-410b-b7b4-528d125c67b4
ms.openlocfilehash: 8a96c30103d46c23f3b678a2fa84abf34445dd11
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221028"
---
# <a name="compiler-error-c2010"></a>编译器错误 C2010

"character"：宏形参表中的意外

在宏定义的形参列表中错误地使用了该字符。 删除字符以解决错误。

下面的示例生成 C2010：

```cpp
// C2010.cpp
// compile with: /c
#define mymacro(a|) (2*a)   // C2010
#define mymacro(a) (2*a)   // OK
```
