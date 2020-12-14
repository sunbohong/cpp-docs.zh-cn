---
description: 了解更多：编译器错误 C2007
title: 编译器错误 C2007
ms.date: 11/04/2016
f1_keywords:
- C2007
helpviewer_keywords:
- C2007
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
ms.openlocfilehash: fa2ad780269079ef081f22d2c222e106443200e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298482"
---
# <a name="compiler-error-c2007"></a>编译器错误 C2007

\#定义语法

后，不会出现标识符 `#define` 。 若要解决此错误，请使用标识符。

下面的示例生成 C2007：

```cpp
// C2007.cpp
#define   // C2007
```

可能的解决方法：

```cpp
// C2007b.cpp
// compile with: /c
#define true 1
```
