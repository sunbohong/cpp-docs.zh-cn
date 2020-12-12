---
description: 了解更多：编译器错误 C2509
title: 编译器错误 C2509
ms.date: 11/04/2016
f1_keywords:
- C2509
helpviewer_keywords:
- C2509
ms.assetid: 339c1fcd-ec4a-456c-9f18-a9b24d9921af
ms.openlocfilehash: d7b6c2f05aaf525bee9572cd921d1fdffe1b0cf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212956"
---
# <a name="compiler-error-c2509"></a>编译器错误 C2509

"identifier"：成员函数在 "class" 中未声明

未在指定的类中声明函数。

## <a name="example"></a>示例

下面的示例生成 C2509。

```cpp
// C2509.cpp
// compile with: /c
struct A {
   virtual int vfunc() = 0;
   virtual int vfunc2() = 0;
};

struct B : private A {
   using A::vfunc;
   virtual int vfunc2();
};

int B::vfunc() { return 1; }   // C2509
int B::vfunc2() { return 1; }   // OK
```
