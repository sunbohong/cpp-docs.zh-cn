---
description: 了解更多：编译器错误 C2767
title: 编译器错误 C2767
ms.date: 11/04/2016
f1_keywords:
- C2767
helpviewer_keywords:
- C2767
ms.assetid: e8f84178-a160-4d71-a236-07e4fcc11e96
ms.openlocfilehash: 4acd75d1b7782a7eb694e7b91fc19cac45a6319e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239475"
---
# <a name="compiler-error-c2767"></a>编译器错误 C2767

托管或 WinRTarray 维度不匹配：应为 N 参数 (提供) -M

托管数组或 WinRT 数组的声明的格式不正确。 有关详细信息，请参阅 [数组](../../extensions/arrays-cpp-component-extensions.md)。

下面的示例生成 C2767，并演示如何修复此错误：

```cpp
// C2767.cpp
// compile with: /clr
int main() {
   array<int> ^p1 = new array<int>(2,3); // C2767
   array<int> ^p2 = new array<int>(2);   // OK
}
```
