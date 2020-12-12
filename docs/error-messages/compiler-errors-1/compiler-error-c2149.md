---
description: 了解更多：编译器错误 C2149
title: 编译器错误 C2149
ms.date: 11/04/2016
f1_keywords:
- C2149
helpviewer_keywords:
- C2149
ms.assetid: 7a106dab-d79f-41b9-85be-f36e86e4d2ab
ms.openlocfilehash: c93efe0648ebe064024177d61acd9d07150a1a1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235341"
---
# <a name="compiler-error-c2149"></a>编译器错误 C2149

“identifier”：已命名位域不能具有零宽度

位域只有在未命名时才可以有零宽度。

下面的示例生成 C2149：

```cpp
// C2149.cpp
// compile with: /c
struct C {
   int i : 0;   // C2149
   int j : 2;   // OK
};
```
