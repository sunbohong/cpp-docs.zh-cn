---
description: 了解更多：编译器错误 C2933
title: 编译器错误 C2933
ms.date: 11/04/2016
f1_keywords:
- C2933
helpviewer_keywords:
- C2933
ms.assetid: 394891e3-6b52-4b61-83d2-a1c5125d9bd5
ms.openlocfilehash: be815b24b892cc1ef835654df81c7d47483f3730
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297416"
---
# <a name="compiler-error-c2933"></a>编译器错误 C2933

“class”: type-class-id 重新定义为“identifier”的 typedef 成员

不能将泛型或模板类用作 **`typedef`** 成员。

下面的示例生成 C2933：

```cpp
// C2933.cpp
// compile with: /c
template<class T> struct TC { };
struct MyStruct {
   typedef int TC<int>;   // C2933
};

struct TC2 { };
struct MyStruct2 {
   typedef int TC2;
};
```

使用泛型时也可能发生 C2933：

```cpp
// C2933b.cpp
// compile with: /clr /c
generic<class T> ref struct GC { };
struct MyStruct {
   typedef int GC<int>;   // C2933
};

ref struct GC2 { };
struct MyStruct2 {
   typedef int GC2;
};
```
