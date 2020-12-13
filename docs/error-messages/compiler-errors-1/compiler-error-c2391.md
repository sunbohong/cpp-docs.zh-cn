---
description: 了解更多：编译器错误 C2391
title: 编译器错误 C2391
ms.date: 11/04/2016
f1_keywords:
- C2391
helpviewer_keywords:
- C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
ms.openlocfilehash: 3161cd6ade15817142cc24f38c61fd3e09eb8857
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337573"
---
# <a name="compiler-error-c2391"></a>编译器错误 C2391

"identifier"： "friend" 不能在类型定义过程中使用

**`friend`** 声明包含完整的类声明。 **`friend`** 声明可以指定成员函数或详细的类型说明符，但不能指定完整的类声明。

下面的示例生成 C2326:

```cpp
// C2391.cpp
// compile with: /c
class D {
   void func( int );
};

class A {
   friend class B { int i; };   // C2391

   // OK
   friend class C;
   friend void D::func(int);
};
```
