---
description: 了解更多：编译器错误 C2811
title: 编译器错误 C2811
ms.date: 11/04/2016
f1_keywords:
- C2811
helpviewer_keywords:
- C2811
ms.assetid: 6a44b18e-44c1-49d8-9b99-e0545b9a6e7d
ms.openlocfilehash: 02b4770b08bdfc9ee15386874ebba2265716536d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194847"
---
# <a name="compiler-error-c2811"></a>编译器错误 C2811

"type1"：不能从 "type2" 继承，ref 类只能从 ref 类或接口类继承

尝试使用非托管类作为托管类的基类。

下面的示例生成 C2811：

```cpp
// C2811.cpp
// compile with: /clr /c
struct S{};
ref struct T {};
ref class C : public S {};   // C2811
ref class D : public T {};   // OK
```
