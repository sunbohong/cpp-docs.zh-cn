---
description: 了解更多：编译器错误 C2563
title: 编译器错误 C2563
ms.date: 11/04/2016
f1_keywords:
- C2563
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
ms.openlocfilehash: 2243e0820b2e69d6bc05351fdba4600188a3ac08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209147"
---
# <a name="compiler-error-c2563"></a>编译器错误 C2563

形参表中不匹配

函数的形参列表 (或指向函数的指针) 与其他函数 (或指向成员函数) 的指针不匹配。 因此，无法对函数或指针赋值。

下面的示例生成 C2563：

```cpp
// C2563.cpp
void func( int );
void func( int, int );
int main() {
   void *fp();
   fp = func;   // C2563
}
```
