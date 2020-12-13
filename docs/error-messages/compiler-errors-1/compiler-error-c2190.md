---
description: 了解更多：编译器错误 C2190
title: 编译器错误 C2190
ms.date: 11/04/2016
f1_keywords:
- C2190
helpviewer_keywords:
- C2190
ms.assetid: 34e15f85-d979-4948-80fc-46c414508a70
ms.openlocfilehash: aeee732ff819746afa3bc572d4c090a694707afd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337692"
---
# <a name="compiler-error-c2190"></a>编译器错误 C2190

第一个参数列表比第二个长

第二次使用较短的参数列表声明了 C 函数。 C 不支持重载函数。

下面的示例生成 C2190：

```c
// C2190.c
// compile with: /Za /c
void func( int, float );
void func( int  );   // C2190, different parameter list
void func2( int  );   // OK
```
