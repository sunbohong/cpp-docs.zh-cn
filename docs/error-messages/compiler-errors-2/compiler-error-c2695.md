---
description: 了解更多：编译器错误 C2695
title: 编译器错误 C2695
ms.date: 11/04/2016
f1_keywords:
- C2695
helpviewer_keywords:
- C2695
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
ms.openlocfilehash: 6137749725de5c2285cb5defd84fd7c8c0f2e237
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326638"
---
# <a name="compiler-error-c2695"></a>编译器错误 C2695

"function1"：重写虚函数不同于 "function2" （仅通过调用约定）

派生类中的函数签名不能重写基类中的函数，也不能更改调用约定。

下面的示例生成 C2695：

```cpp
// C2695.cpp
class C {
   virtual void __fastcall func();
};

class D : public C {
   virtual void __clrcall func();   // C2695
};
```
