---
description: 了解详细信息：编译器警告 (等级 1) C4172
title: 编译器警告 (等级 1) C4172
ms.date: 11/04/2016
f1_keywords:
- C4172
helpviewer_keywords:
- C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
ms.openlocfilehash: 7bcfe460150e543c1e3fb6a93ed6656619b5cb13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266931"
---
# <a name="compiler-warning-level-1-c4172"></a>编译器警告 (等级 1) C4172

返回局部变量或临时变量的地址

函数返回局部变量或临时对象的地址。 当函数返回时，局部变量和临时对象将被销毁，因此返回的地址无效。

重新设计函数，使其不返回本地对象的地址。

下面的示例生成 C4172：

```cpp
// C4172.cpp
// compile with: /W1 /LD
float f = 10;

const double& bar() {
// try the following line instead
// const float& bar() {
   return f;   // C4172
}
```
