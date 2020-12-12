---
description: 了解更多：编译器错误 C2619
title: 编译器错误 C2619
ms.date: 11/04/2016
f1_keywords:
- C2619
helpviewer_keywords:
- C2619
ms.assetid: c826f8ab-d66a-4b79-a0b2-93b0af8c41ac
ms.openlocfilehash: 2ca9a8379901703299e89e71671ec0270c1ff1e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123535"
---
# <a name="compiler-error-c2619"></a>编译器错误 C2619

“标识符”：匿名结构或联合中不允许使用静态数据成员

已声明匿名结构或联合的成员 **`static`** 。

下面的示例生成 C2619，并演示如何通过删除 static 关键字修复此错误。

```cpp
// C2619.cpp
int main() {
   union { static int j; };  // C2619
   union { int j; };  // OK
}
```
