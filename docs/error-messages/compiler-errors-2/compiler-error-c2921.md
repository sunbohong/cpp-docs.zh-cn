---
description: 了解更多：编译器错误 C2921
title: 编译器错误 C2921
ms.date: 11/04/2016
f1_keywords:
- C2921
helpviewer_keywords:
- C2921
ms.assetid: 323642a0-bfc4-4942-9f41-c3adf5c54296
ms.openlocfilehash: 95c47b1446973db77e4567dce0d4af8adf321672
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270298"
---
# <a name="compiler-error-c2921"></a>编译器错误 C2921

重定义：“class”：类 template 或 generic 重新声明为“type”

generic 或 template 类具有多个不等效的声明。 要解决此错误，请对不同的类型使用不同的名称，或删除类型名称的重定义。

以下示例生成 C2921：

```cpp
// C2921.cpp
// compile with: /c
template <class T> struct TC2 {};
typedef int TC2;   // C2921
// try the following line instead
// typedef struct TC2<int> x;   // OK - declare a template instance
```

使用 generic 时，也可能发生 C2921。

```cpp
// C2921b.cpp
// compile with: /clr /c
generic <class T> ref struct GC2 {};
typedef int GC2;   // C2921
// try the following line instead
// typedef ref struct GC2<int> x;
```
