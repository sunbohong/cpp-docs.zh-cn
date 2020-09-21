---
title: 编译器错误 C2524
ms.date: 11/04/2016
f1_keywords:
- C2524
helpviewer_keywords:
- C2524
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
ms.openlocfilehash: 57445fec5ee5bb55ac3d16ee21a0e29eb4b21ed1
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743342"
---
# <a name="compiler-error-c2524"></a>编译器错误 C2524

"析构函数"：析构函数/终结器必须具有 "void" 参数列表

析构函数或终结器的参数列表不是 [void](../../cpp/void-cpp.md)。 不允许使用其他参数类型。

## <a name="examples"></a>示例

下面的代码将 C2524。

```cpp
// C2524.cpp
// compile with: /c
class A {
   A() {}
   ~A(int i) {}    // C2524
   // try the following line instead
   // ~A() {}
};
```

下面的代码将 C2524。

```cpp
// C2524_b.cpp
// compile with: /clr /c
ref struct I1 {
protected:
   !I1(int i);   // C2524
   // try the following line instead
   // !I1();
};
```
