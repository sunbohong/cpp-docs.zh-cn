---
description: 了解更多：编译器错误 C2462
title: 编译器错误 C2462
ms.date: 11/04/2016
f1_keywords:
- C2462
helpviewer_keywords:
- C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
ms.openlocfilehash: f85d8f2e38c38043765b29b6e766c0cbd4fef1fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341810"
---
# <a name="compiler-error-c2462"></a>编译器错误 C2462

"identifier"：不能在 "new 表达式" 中定义类型

不能在运算符的操作数字段中定义类型 **`new`** 。 将类型定义置于单独的语句中。

下面的示例生成 C2462：

```cpp
// C2462.cpp
int main() {
   new struct S { int i; };   // C2462
}
```
