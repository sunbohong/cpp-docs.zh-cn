---
description: 了解更多：编译器错误 C2931
title: 编译器错误 C2931
ms.date: 11/04/2016
f1_keywords:
- C2931
helpviewer_keywords:
- C2931
ms.assetid: 33430407-b149-4ba3-baf8-b0dae1ea3a5d
ms.openlocfilehash: a4d659a0529fa80affc6749d150b9a567d015d90
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320326"
---
# <a name="compiler-error-c2931"></a>编译器错误 C2931

“class”: type-class-id 重新定义为“identifier”的成员函数

不能使用泛型或模板类作为另一个类的成员函数。

如果大括号匹配不正确，则可能导致此错误。

下面的示例生成 C2931：

```cpp
// C2931.cpp
// compile with: /c
template<class T>
struct TC { };
struct MyStruct {
   void TC<int>();   // C2931
};

struct TC2 { };
struct MyStruct2 {
   void TC2();
};
```

使用泛型时也可能发生 C2931：

```cpp
// C2931b.cpp
// compile with: /clr /c
generic<class T> ref struct GC {};
struct MyStruct {
   void GC<int>();   // C2931
   void GC2();   // OK
};
```
