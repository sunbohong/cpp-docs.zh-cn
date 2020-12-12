---
description: 详细了解：编译器警告 (级别 4) C4706
title: 编译器警告（等级 4）C4706
ms.date: 11/04/2016
f1_keywords:
- C4706
helpviewer_keywords:
- C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
ms.openlocfilehash: ca614d0ca55dcfa22ec31df78ebe2be904ffd9e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208523"
---
# <a name="compiler-warning-level-4-c4706"></a>编译器警告（等级 4）C4706

条件表达式内的赋值

条件表达式中的测试值是赋值的结果。

赋值的值 (赋值) 左侧的值，可在其他表达式（包括测试表达式）中合法使用。

下面的示例生成 C4706：

```cpp
// C4706a.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( a  = b ) // C4706
   {
   }
}
```

即使在测试条件两边加两个括号，也会出现此警告：

```cpp
// C4706b.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( ( a  =  b ) ) // C4706
   {
   }
}
```

如果打算测试关系而不进行赋值，请使用 `==` 运算符。 例如，下面的行测试和 b 是否相等：

```cpp
// C4706c.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( a == b )
   {
   }
}
```

如果要使测试值成为赋值的结果，请测试以确保赋值非零或非 null。 例如，下面的代码不会生成此警告：

```cpp
// C4706d.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( ( a = b ) != 0 )
   {
   }
}
```
