---
description: 了解更多：编译器错误 C2936
title: 编译器错误 C2936
ms.date: 11/04/2016
f1_keywords:
- C2936
helpviewer_keywords:
- C2936
ms.assetid: 5d1ba0fc-0c78-4a37-a83b-1ef8527763be
ms.openlocfilehash: 2c01886ac02cdd772e7c92faa15dbd015aa6e6e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323033"
---
# <a name="compiler-error-c2936"></a>编译器错误 C2936

“class”：type-class-id 被重新定义为了全局数据变量

不能将泛型或模板类用作全局数据变量。

如果大括号匹配不正确，则可能导致此错误。

下面的示例生成 C2936：

```cpp
// C2936.cpp
// compile with: /c
template<class T> struct TC { };
int TC<int>;   // C2936

// OK
struct TC2 { };
int TC2;
```

使用泛型时，也可能会生成 C2936：

```cpp
// C2936b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};
int GC<int>;   // C2936

// OK
ref struct GC2 {};
int GC2;
```
