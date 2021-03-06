---
description: 了解更多：编译器错误 C2942
title: 编译器错误 C2942
ms.date: 11/04/2016
f1_keywords:
- C2942
helpviewer_keywords:
- C2942
ms.assetid: 13abf744-8fa1-450d-886d-e5717c04956e
ms.openlocfilehash: d68db30f1b70aed20e2501c88bddaf00bb330149
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249589"
---
# <a name="compiler-error-c2942"></a>编译器错误 C2942

“class”：type-class-id 重新定义为函数的形参

不能将泛型或模板类用作形参。 不能直接将参数传递到泛型或模板类的构造函数。

下面的示例生成 C2942：

```

// C2942.cpp
// compile with: /c
template<class T>
struct TC {};
void f(int TC<int>) {}   // C2942

// OK
struct TC2 {};
void f(TC2 i) {}
```

使用泛型时也可能发生 C2942：

```cpp
// C2942b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};
void f(int GC<int>) {}   // C2942
ref struct GC2 { };
void f(int GC2) {}
```
