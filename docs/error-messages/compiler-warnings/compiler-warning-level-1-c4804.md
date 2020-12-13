---
description: 了解详细信息：编译器警告 (等级 1) C4804
title: 编译器警告（等级 1）C4804
ms.date: 11/04/2016
f1_keywords:
- C4804
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
ms.openlocfilehash: 0e1260df9327e714c487159b7c0c8c1a1168bad9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334917"
---
# <a name="compiler-warning-level-1-c4804"></a>编译器警告（等级 1）C4804

"operation"：在操作中使用类型 "bool" 不安全

当你 **`bool`** 以意外方式使用变量或值时，将出现此警告。 例如，如果 (**-**) 或补码运算符 () 中使用运算符（如负一元运算符），则生成 C4804 `~` 。 编译器将计算表达式的值。

## <a name="example"></a>示例

下面的示例生成 C4804：

```cpp
// C4804.cpp
// compile with: /W1

int main()
{
   bool i = true;
   if (-i)   // C4804, remove the '-' to resolve
   {
      i = false;
   }
}
```
