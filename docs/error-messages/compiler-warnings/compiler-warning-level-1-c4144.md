---
description: 了解详细信息：编译器警告 (等级 1) C4144
title: 编译器警告 (等级 1) C4144
ms.date: 11/04/2016
f1_keywords:
- C4144
helpviewer_keywords:
- C4144
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
ms.openlocfilehash: 11f276d4790c11654655fea7cf814dfb30a6787b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136300"
---
# <a name="compiler-warning-level-1-c4144"></a>编译器警告 (等级 1) C4144

"expression"：关系表达式用作 switch 表达式

指定的关系表达式用作 [switch](../../cpp/switch-statement-cpp.md) 语句的控制表达式。 将为关联的 case 语句提供布尔值。 下面的示例生成 C4144：

```cpp
// C4144.cpp
// compile with: /W1
int main()
{
   int i = 0;
   switch(!i) {   // C4144, remove the ! to resolve
      case 1:
         break;
      default:
         break;
   }
}
```
