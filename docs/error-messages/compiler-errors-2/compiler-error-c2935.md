---
description: 了解更多：编译器错误 C2935
title: 编译器错误 C2935
ms.date: 11/04/2016
f1_keywords:
- C2935
helpviewer_keywords:
- C2935
ms.assetid: e11ef90d-0756-4e43-8a09-4974c6aa72a3
ms.openlocfilehash: 853c1e51444454ffdbd09e8387d47eb9770d7fa7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320300"
---
# <a name="compiler-error-c2935"></a>编译器错误 C2935

“class”：type-class-id 重新定义为全局函数

不能将泛型或模板类用作全局函数。

如果大括号匹配不正确，则可能导致此错误。

以下示例生成 C2935：

```cpp
// C2935.cpp
// compile with: /c
template<class T>
struct TC {};
void TC<int>() {}   // C2935

// OK
struct TC2 {};
void TC2() {}
```

使用泛型时也可能发生 C2935：

```cpp
// C2935b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC { };
void GC<int>() {}   // C2935
void GC() {}   // OK
```
