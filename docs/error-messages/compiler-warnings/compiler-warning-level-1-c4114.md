---
description: 了解详细信息：编译器警告 (等级 1) C4114
title: 编译器警告 (等级 1) C4114
ms.date: 11/04/2016
f1_keywords:
- C4114
helpviewer_keywords:
- C4114
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
ms.openlocfilehash: 7d1d7696fabdf8e5114ba733f7bf6de53353bcb4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267438"
---
# <a name="compiler-warning-level-1-c4114"></a>编译器警告 (等级 1) C4114

多次使用同一类型限定符

类型声明或定义多次使用类型限定符 (**`const`** 、 **`volatile`** 、 **`signed`** 或 **`unsigned`**) 。 这会导致 Microsoft extension (/Ze) 出现警告，在 ANSI 兼容性 (/Za) 下出现错误。

下面的示例生成 C4114：

```cpp
// C4114.cpp
// compile with: /W1 /c
volatile volatile int i;   // C4114
```

下面的示例生成 C4114：

```cpp
// C4114_b.cpp
// compile with: /W1 /c
static const int const * ii;   // C4114
static const int * const iii;   // OK
```
