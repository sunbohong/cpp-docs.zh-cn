---
description: 了解更多：编译器错误 C2989
title: 编译器错误 C2989
ms.date: 11/04/2016
f1_keywords:
- C2989
helpviewer_keywords:
- C2989
ms.assetid: 936303d8-eb3b-4746-82ec-2f18020a6f64
ms.openlocfilehash: 38838630f5be23698de099d8c40f7e9b96bc2b13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338610"
---
# <a name="compiler-error-c2989"></a>编译器错误 C2989

"class"：类类型已声明为非类类型

类泛型或模板重新定义非模板或非泛型类。 检查标头文件中的冲突。

下面的示例生成 C2989：

```cpp
// C2989.cpp
// compile with: /c
class C{};

template <class T>
class C{};  // C2989
class C2{};
```

使用泛型时也可能发生 C2989：

```cpp
// C2989b.cpp
// compile with: /clr /c
ref class GC1;

generic <typename T> ref class GC1;   // C2989
template <typename T> ref class GC2;

generic <typename T> ref class GC2;   // C2989
generic <typename T> ref class GCb;
template <typename T> ref class GC2;
generic <typename T> ref class GCc;
```
