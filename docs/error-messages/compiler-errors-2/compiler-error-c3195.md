---
description: 了解更多：编译器错误 C3195
title: 编译器错误 C3195
ms.date: 11/04/2016
f1_keywords:
- C3195
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
ms.openlocfilehash: 691aa50fcb091f240253363a23671ac4db70894f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203791"
---
# <a name="compiler-error-c3195"></a>编译器错误 C3195

“operator”: 被保留并且不能用作 ref 类或值类型的成员。 必须使用“operator”关键字定义 CLR 或 WinRT 运算符

编译器检测到了使用 C++ 托管扩展语法的运算符定义。 必须将 c + + 语法用于运算符。

下面的示例生成 C3195，并演示如何修复此错误：

```cpp
// C3195.cpp
// compile with: /clr /LD
#using <mscorlib.dll>
value struct V {
   static V op_Addition(V v, int i);   // C3195
   static V operator +(V v, char c);   // OK for new C++ syntax
};
```
