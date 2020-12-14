---
description: 了解详细信息：编译器警告 (等级 1) C4461
title: 编译器警告（第 1 级）C4461
ms.date: 11/04/2016
f1_keywords:
- C4461
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
ms.openlocfilehash: 2efb92ca26f9e6cf76f7777c8a50ac657f73554d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311001"
---
# <a name="compiler-warning-level-1-c4461"></a>编译器警告（第 1 级）C4461

"type"：此类具有终结器 "finalizer"，但没有析构函数 "dtor"

类型中是否存在终结器意味着要删除的资源。 除非在对象超出范围后，公共语言运行时才会从类型的析构函数中显式调用终结器，否则，公共语言运行时将确定何时运行终结器。

如果在类型中定义析构函数并从析构函数中显式调用终结器，则可以确定运行终结器。

有关详细信息，请参阅 [析构函数和终结](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)器。

## <a name="example"></a>示例

下面的示例生成 C4461。

```cpp
// C4461.cpp
// compile with: /W1 /clr /c
ref class A {
protected:
   !A() {}   // C4461
};

// OK
ref struct B {
   ~B() {
      B::!B();
   }

   !B() {}
};
```
