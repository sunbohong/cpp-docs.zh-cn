---
description: 了解更多：编译器错误 C2939
title: 编译器错误 C2939
ms.date: 11/04/2016
f1_keywords:
- C2939
helpviewer_keywords:
- C2939
ms.assetid: 455b050b-f2dc-4b5b-bd6a-e1f81d3d1644
ms.openlocfilehash: 465d2d9535a1c8f393e21b4ef48707f8e5fab89b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323020"
---
# <a name="compiler-error-c2939"></a>编译器错误 C2939

“class”：type-class-id 重新定义为局部数据变量

不能将泛型或模板类用作局部数据变量。

如果大括号匹配不正确，则可能导致此错误。

下面的示例生成 C2939：

```cpp
// C2939.cpp
template<class T>
struct TC { };
int main() {
   int TC<int>;   // C2939
   int TC;   // OK
}
```

使用 generic 时，也可能发生 C2939：

```cpp
// C2939b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };

int main() {
   int GC<int>;   // C2939
   int GC;   // OK
}
```
