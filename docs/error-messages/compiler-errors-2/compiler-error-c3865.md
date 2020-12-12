---
description: 了解更多：编译器错误 C3865
title: 编译器错误 C3865
ms.date: 11/04/2016
f1_keywords:
- C3865
helpviewer_keywords:
- C3865
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
ms.openlocfilehash: 956cbfeb5bac97cae7e9a9a411c29326062e15b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222874"
---
# <a name="compiler-error-c3865"></a>编译器错误 C3865

"calling_convention"：只能用在本机成员函数上

调用约定用于作为全局函数或托管成员函数的函数。 调用约定只能用于本机 (不是托管) 成员函数。

有关详细信息，请参阅 [调用约定](../../cpp/calling-conventions.md)。

下面的示例生成 C3865：

```cpp
// C3865.cpp
// compile with: /clr
// processor: x86
void __thiscall Func(){}   // C3865

// OK
struct MyType {
   void __thiscall Func(){}
};
```
