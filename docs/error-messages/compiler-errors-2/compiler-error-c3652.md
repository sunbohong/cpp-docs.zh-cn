---
description: 了解更多：编译器错误 C3652
title: 编译器错误 C3652
ms.date: 11/04/2016
f1_keywords:
- C3652
helpviewer_keywords:
- C3652
ms.assetid: 15d68737-177e-41f1-80e0-7c3e2afdf0fc
ms.openlocfilehash: d7ef611f58a62cd7a209ee680390c147759c9b64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203661"
---
# <a name="compiler-error-c3652"></a>编译器错误 C3652

"override"：显式重写的函数必须是虚拟的

显式重写的函数必须是虚拟的。 有关详细信息，请参阅 [显式重写](../../extensions/explicit-overrides-cpp-component-extensions.md)。

下面的示例生成 C3652：

```cpp
// C3652.cpp
// compile with: /clr /c
public interface class I {
   void f();
};

public ref struct R : I {
   void f() = I::f {}   // C3652
   // try the following line instead
   // virtual void f() = I::f {}
};
```
