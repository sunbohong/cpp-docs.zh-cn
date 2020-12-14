---
description: 了解更多：编译器错误 C2438
title: 编译器错误 C2438
ms.date: 11/04/2016
f1_keywords:
- C2438
helpviewer_keywords:
- C2438
ms.assetid: 3a0ab3ba-d0e4-4d8f-971d-e503397cc827
ms.openlocfilehash: 1400ee013e5d507f7fdfe288b97db10ec8216085
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189881"
---
# <a name="compiler-error-c2438"></a>编译器错误 C2438

"identifier"：无法通过构造函数初始化静态类数据

构造函数用于初始化类的静态成员。 静态成员必须在类声明之外的定义中进行初始化。

下面的示例生成 C2438：

```cpp
// C2438.cpp
struct X {
   X(int i) : j(i) {}   // C2438
   static int j;
};

int X::j;

int main() {
   X::j = 1;
}
```
