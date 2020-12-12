---
description: 了解更多：编译器错误 C2570
title: 编译器错误 C2570
ms.date: 11/04/2016
f1_keywords:
- C2570
helpviewer_keywords:
- C2570
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
ms.openlocfilehash: faebc117991262c8fff94ef75f18d6e59c884315
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209017"
---
# <a name="compiler-error-c2570"></a>编译器错误 C2570

"identifier"：联合不能有基类

联合派生自类、结构或联合。 这是不允许的。 改为将派生类型声明为类或结构。

下面的示例生成 C2570：

```cpp
// C2570.cpp
// compile with: /c
class base {};
union hasPubBase : public base {};   // C2570
union hasNoBase {};   // OK
```
