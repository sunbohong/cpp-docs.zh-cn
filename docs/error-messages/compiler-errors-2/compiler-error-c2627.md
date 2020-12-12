---
description: 了解更多：编译器错误 C2627
title: 编译器错误 C2627
ms.date: 11/04/2016
f1_keywords:
- C2627
helpviewer_keywords:
- C2627
ms.assetid: 7fc6c5ac-c7c9-4f0b-ad52-f52252526458
ms.openlocfilehash: 4f09e2b76376871dab93e0736c8a0ca6dbb2b5a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174567"
---
# <a name="compiler-error-c2627"></a>编译器错误 C2627

"function"：匿名联合中不允许使用成员函数

[匿名联合](../../cpp/unions.md#anonymous_unions)不能具有成员函数。

下面的示例生成 C2627：

```cpp
// C2627.cpp
int main() {
   union { void f(){} };   // C2627
   union X { void f(){} };
}
```
