---
description: 了解更多：编译器错误 C2032
title: 编译器错误 C2032
ms.date: 11/04/2016
f1_keywords:
- C2032
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
ms.openlocfilehash: cb39a539dc1e360f70cc2b217d50f3a1eabcf0f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175451"
---
# <a name="compiler-error-c2032"></a>编译器错误 C2032

"identifier"：函数不能是结构/联合 "structorunion" 的成员

结构或联合具有成员函数，它在 c + + 中是允许的，但在 C 中是不允许的。若要解决此错误，请将编译为 c + + 程序或删除成员函数。

下面的示例生成 C2032：

```c
// C2032.c
struct z {
   int i;
   void func();   // C2032
};
```

可能的解决方法：

```c
// C2032b.c
// compile with: /c
struct z {
   int i;
};
```
