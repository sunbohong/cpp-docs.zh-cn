---
description: 了解更多：编译器错误 C2791
title: 编译器错误 C2791
ms.date: 11/04/2016
f1_keywords:
- C2791
helpviewer_keywords:
- C2791
ms.assetid: 938ad1fb-75d9-4ce2-ad92-83d6249005b5
ms.openlocfilehash: 0f5bd93c1c6ee32399da793147a18e9225b5fcb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297767"
---
# <a name="compiler-error-c2791"></a>编译器错误 C2791

非法使用 "super"： "class" 没有任何基类

关键字 [super](../../cpp/super.md) 用于不包含任何基类的类的成员函数的上下文中。

下面的示例生成 C2791：

```cpp
// C2791.cpp
struct D {
   void mf() {
      __super::mf();   // C2791
   }
};
```
