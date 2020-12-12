---
description: 了解详细信息：编译器警告 (等级 1) C4630
title: 编译器警告（等级 1）C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 49a73dcd3ce11fefa1d4275e57ad98092c242d8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318905"
---
# <a name="compiler-warning-level-1-c4630"></a>编译器警告（等级 1）C4630

"symbol"：成员定义上的 "extern" 存储类说明符非法

数据成员或成员函数定义为 **`extern`** 。 成员不能是外部的，但整个对象都可以。 编译器将忽略 **`extern`** 关键字。 下面的示例生成 C4630：

```cpp
// C4630.cpp
// compile with: /W1 /LD
class A {
   void func();
};

extern void A::func() {   // C4630, remove 'extern' to resolve
}
```
