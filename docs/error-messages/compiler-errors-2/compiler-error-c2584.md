---
description: 了解更多：编译器错误 C2584
title: 编译器错误 C2584
ms.date: 11/04/2016
f1_keywords:
- C2584
helpviewer_keywords:
- C2584
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
ms.openlocfilehash: 7820019c3ec49928f59980adbd9ec814d67c3499
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177674"
---
# <a name="compiler-error-c2584"></a>编译器错误 C2584

"Class"：无法访问直接基 "Base2";已是 "Base1" 的基

`Class` 已直接从派生 `Base1` 。 `Base2` 也派生自 `Base1` 。 `Class` 无法从派生 `Base2` ，因为这将意味着继承 (间接 `Base1` 再次) ，这是不合法的，因为已 `Base1` 是直接基类。

## <a name="example"></a>示例

下面的示例生成 C2584。

```cpp
// C2584.cpp
// compile with: /c
struct A1 {
   virtual int MyFunction();
};

struct A2 {
    virtual int MyFunction();
};

struct B1: public virtual A1, virtual A2 {
    virtual int MyFunction();
};

struct B2: public virtual A2, virtual A1 {
    virtual int MyFunction();
};

struct C: virtual B1, B2 {
    virtual int MyFunction();
};

struct Z : virtual B2, virtual C {   // C2584
// try the following line insted
// struct Z : virtual C {
    virtual int MyFunction();
};
```
