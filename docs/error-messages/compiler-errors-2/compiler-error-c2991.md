---
description: 了解更多：编译器错误 C2991
title: 编译器错误 C2991
ms.date: 11/04/2016
f1_keywords:
- C2991
helpviewer_keywords:
- C2991
ms.assetid: a87e4404-26e8-4927-b3ee-5d02b3b8bee1
ms.openlocfilehash: 9f42d96a15869b656abfff21a921ec340aa6ce1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338593"
---
# <a name="compiler-error-c2991"></a>编译器错误 C2991

重定义类型形参“parameter”

`parameter`的两个泛型或模板定义之间存在类型冲突。 定义多个泛型参数或模板参数时，必须使用等效类型。

下面的示例生成 C2991：

```cpp
// C2991.cpp
// compile with: /c
template<class T, class T> struct TC {};   // C2991
// try the following line instead
// template<class T, class T2> struct TC {};
```

使用泛型时，也可能发生 C2991：

```cpp
// C2991b.cpp
// compile with: /clr /c
generic<class T,class T> ref struct GC {};   // C2991
// try the following line instead
// generic<class T,class T2> ref struct GC {};
```
