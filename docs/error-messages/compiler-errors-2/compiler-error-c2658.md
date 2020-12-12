---
description: 了解更多：编译器错误 C2658
title: 编译器错误 C2658
ms.date: 11/04/2016
f1_keywords:
- C2658
helpviewer_keywords:
- C2658
ms.assetid: 638368e8-7893-4a14-abec-13c768a9543a
ms.openlocfilehash: 6f86bb2147d13a0192cb7272e3ac2f3f580b1493
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286041"
---
# <a name="compiler-error-c2658"></a>编译器错误 C2658

"member"：匿名结构/联合中的重定义

两个匿名结构或联合包含具有相同标识符但类型不同的成员声明。 在 [/za](../../build/reference/za-ze-disable-language-extensions.md)下，对于具有相同标识符和类型的成员，也会出现此错误。

下面的示例生成 C2658：

```cpp
// C2658.cpp
// compile with: /c
struct X {
   union { // can be struct too
      int i;
   };
   union {
      int i;   // Under /Za, C2658
      // int i not needed here because it is defined in the first union
   };
};

struct Z {
   union {
      char *i;
   };

   union {
      void *i;   // C2658 redefinition of 'i'
      // try the following line instead
      // void *ii;
   };
};
```
