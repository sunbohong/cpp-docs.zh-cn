---
description: 了解更多：编译器错误 C2691
title: 编译器错误 C2691
ms.date: 11/04/2016
f1_keywords:
- C2691
helpviewer_keywords:
- C2691
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
ms.openlocfilehash: 575651d1da871a0514585fea010ef3fe98e8a3cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344323"
---
# <a name="compiler-error-c2691"></a>编译器错误 C2691

"数据类型"：托管或 WinRTarray 不能有此元素类型

托管数组元素或 WinRT 数组元素的类型可以是值类型或引用类型。

以下示例生成 C2691：

```cpp
// C2691a.cpp
// compile with: /clr
class A {};

int main() {
   array<A>^ a1 = gcnew array<A>(20);   // C2691
   array<int>^ a2 = gcnew array<int>(20);   // value type OK
}
```
