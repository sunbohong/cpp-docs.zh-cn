---
description: 了解更多：编译器错误 C2847
title: 编译器错误 C2847
ms.date: 11/04/2016
f1_keywords:
- C2847
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
ms.openlocfilehash: fc9b7a75d662778bc532bb35e4520fb5627c9f2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260210"
---
# <a name="compiler-error-c2847"></a>编译器错误 C2847

无法将 sizeof 应用到托管或 WinRT 类型“类”

[Sizeof](../../cpp/sizeof-operator.md)运算符在编译时获取对象的值。 由于托管或 WinRT 类的大小、接口或值类型是动态的，因此在编译时无法得知。

例如，以下示例生成 C2847：

```cpp
// C2847.cpp
// compile with: /clr
ref class A {};

int main() {
   A ^ xA = gcnew A;
   sizeof(*xA);   // C2847 cannot use sizeof on managed object
}
```
