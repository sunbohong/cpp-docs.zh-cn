---
description: 了解更多：编译器错误 C2923
title: 编译器错误 C2923
ms.date: 11/04/2016
f1_keywords:
- C2923
helpviewer_keywords:
- C2923
ms.assetid: 6b92933b-13ef-4124-99d9-b89f9fdae030
ms.openlocfilehash: 7897ba68998f88f82144278e79c97d8fec9f85d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270272"
---
# <a name="compiler-error-c2923"></a>编译器错误 C2923

“type”: 对于参数“param”，“identifier”不是有效的模板类型参数

参数列表缺少实例化模板或泛型所需的类型。 检查模板或泛型声明。

下面的示例生成 C2923：

```cpp
// C2923.cpp
template <class T> struct TC {};
int x;
int main() {
   TC<x>* tc2;   // C2923
   TC<int>* tc2;   // OK
}
```

使用泛型时，也可能会发生 C2923：

```cpp
// C2923b.cpp
// compile with: /clr /c
generic <class T> ref struct GC {};

int x;

int main() {
   GC<x>^ gc2;   // C2923
   GC<int>^ gc2;   // OK
}
```
