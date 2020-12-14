---
description: 了解更多：编译器错误 C2726
title: 编译器错误 C2726
ms.date: 11/04/2016
f1_keywords:
- C2726
helpviewer_keywords:
- C2726
ms.assetid: f0191bb7-c175-450b-bf09-a3213db96d09
ms.openlocfilehash: 9318ea0cbf695f1c42253a680143edb7b541d25e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245325"
---
# <a name="compiler-error-c2726"></a>编译器错误 C2726

“gcnew”只能用于创建具有托管或 WinRT 类型的对象

不能在垃圾回收堆上创建本机类型的实例。

下面的示例生成 C2726，并演示如何修复此错误：

```cpp
// C2726.cpp
// compile with: /clr
using namespace System;
class U {};
ref class V {};
value class W {};

int main() {
   U* pU = gcnew U;    // C2726
   U* pU2 = new U;   // OK
   V^ p2 = gcnew V;   // OK
   W p3;   // OK

}
```
