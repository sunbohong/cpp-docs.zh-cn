---
description: 了解更多：编译器错误 C2794
title: 编译器错误 C2794
ms.date: 11/04/2016
f1_keywords:
- C2794
helpviewer_keywords:
- C2794
ms.assetid: d508191c-9044-4c6a-9119-4bca668c0b93
ms.openlocfilehash: 68f0c20e7942a32ede42fa8d7d069164d083377a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297650"
---
# <a name="compiler-error-c2794"></a>编译器错误 C2794

"function"：不是 "class" 的任何直接或间接基类的成员

您尝试使用 [super](../../cpp/super.md) 来调用不存在的成员函数。

下面的示例生成 C2794

```cpp
// C2794.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super::f();  // C2794
   }
};
```
