---
description: 了解更多：编译器错误 C2990
title: 编译器错误 C2990
ms.date: 11/04/2016
f1_keywords:
- C2990
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
ms.openlocfilehash: 80aa15940420e9d3e452f2c3a93eefe94fd1561b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328246"
---
# <a name="compiler-error-c2990"></a>编译器错误 C2990

"class"：非类类型已声明为类类型

非泛型或模板类重新定义泛型或模板类。 检查标头文件中的冲突。

下面的示例生成 C2990：

```cpp
// C2990.cpp
// compile with: /c
template <class T>
class C{};
class C{};   // C2990
```

使用泛型时也可能发生 C2990：

```cpp
// C2990b.cpp
// compile with: /clr /c
generic <class T>
ref struct GC;

ref struct GC {};   // C2990
```

由于 Visual Studio 2005 的 Microsoft c + + 编译器中的重大更改，也可能会发生 C2990;编译器现在要求同类型的多个声明对于模板规范是相同的。

下面的示例生成 C2990：

```cpp
// C2990c.cpp
// compile with: /c
template<class T>
class A;

template<class T>
struct A2 {
   friend class A;   // C2990
};

// OK
template<class T>
struct B {
   template<class T>
   friend class A;
};
```
