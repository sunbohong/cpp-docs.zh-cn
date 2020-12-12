---
description: 了解详细信息：编译器警告 (等级 1) C4183
title: 编译器警告 (等级 1) C4183
ms.date: 11/04/2016
f1_keywords:
- C4183
helpviewer_keywords:
- C4183
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
ms.openlocfilehash: 1e9753637d0ee52ef40ce875e4e2d66fbdaab9db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266671"
---
# <a name="compiler-warning-level-1-c4183"></a>编译器警告 (等级 1) C4183

"identifier"：缺少返回类型;假定为返回 "int" 的成员函数

类或结构中成员函数的内联定义没有返回类型。 假定此成员函数的默认返回类型为 **`int`** 。

下面的示例生成 C4183：

```cpp
// C4183.cpp
// compile with: /W1 /c
#pragma warning(disable : 4430)
class MyClass1;
class MyClass2 {
   MyClass1() {};   // C4183
};
```
