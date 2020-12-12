---
description: 了解更多：编译器错误 C2784
title: 编译器错误 C2784
ms.date: 11/04/2016
f1_keywords:
- C2784
helpviewer_keywords:
- C2784
ms.assetid: 3d761fe2-881c-48bd-afae-e2e714e20473
ms.openlocfilehash: dcee0cc2c6c8154bafe4a37fe83c66b1c8d477d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297910"
---
# <a name="compiler-error-c2784"></a>编译器错误 C2784

“declaration”: 对于“type”，无法从“type”推导其模板参数

编译器无法从提供的函数参数确定模板参数。

下面的示例生成 C2784，并演示如何修复此错误：

```cpp
// C2784.cpp
template<class T> class X {};
template<class T> void f(X<T>) {}

int main() {
   X<int> x;
   f(1);   // C2784

   // To fix it, try the following line instead
   f(x);
}
```
