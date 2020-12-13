---
description: 了解更多：编译器错误 C2524
title: 编译器错误 C2524
ms.date: 11/04/2016
f1_keywords:
- C2524
helpviewer_keywords:
- C2524
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
ms.openlocfilehash: 94e974674a5e244168499a50304a07264d23e618
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151133"
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
