---
description: 了解更多：编译器错误 C2603
title: 编译器错误 C2603
ms.date: 11/04/2016
f1_keywords:
- C2603
helpviewer_keywords:
- C2603
ms.assetid: 9ca520d0-f082-4b65-933d-17c3bcf8b02c
ms.openlocfilehash: e28ea581c4c1417972cddc0ce558bd518acb8889
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208783"
---
# <a name="compiler-error-c2603"></a>编译器错误 C2603

> "*function*"：函数中有构造函数/析构函数的块范围静态对象太多

在 Visual Studio 2015 之前的 Microsoft c + + 编译器的版本中，或在指定 [/zc： threadSafeInit](../../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) 选项时，在外部可见内联函数中可以具有的静态对象数限制为31。

若要解决此问题，我们建议你采用最新版本的 Microsoft c + + 编译器工具集，或在可能的情况下删除/Zc： threadSafeInit 选项。 如果无法做到这一点，请考虑将静态对象组合在一起。 如果对象具有相同的类型，请考虑使用该类型的单个静态数组，并根据需要引用单个成员。

## <a name="example"></a>示例

下面的代码生成 C2603，并演示一种解决方法：

```cpp
// C2603.cpp
// Compile by using: cl /W4 /c /Zc:threadSafeInit- C2603.cpp
struct C { C() {} };
extern inline void f1() {
    static C C01, C02, C03, C04, C05, C06, C07, C08, C09, C10;
    static C C11, C12, C13, C14, C15, C16, C17, C18, C19, C20;
    static C C21, C22, C23, C24, C25, C26, C27, C28, C29, C30, C31;
    static C C32;   // C2603 Comment this line out to avoid error
}
```
