---
description: 了解更多：编译器错误 C3634
title: 编译器错误 C3634
ms.date: 11/04/2016
f1_keywords:
- C3634
helpviewer_keywords:
- C3634
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
ms.openlocfilehash: 21407af8a86a3f82331d0f2a1d424457d8bee833
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239241"
---
# <a name="compiler-error-c3634"></a>编译器错误 C3634

"function"：不能定义托管或 WinRTclass 的抽象方法

可在托管或 WinRT 类中声明一个抽象方法，但不能定义它。

## <a name="example"></a>示例

以下示例生成 C3634：

```cpp
// C3634.cpp
// compile with: /clr
ref class C {
   virtual void f() = 0;
};

void C::f() {   // C3634 - don't define managed class' pure virtual method
}
```
