---
description: 了解更多：编译器错误 C3269
title: 编译器错误 C3269
ms.date: 11/04/2016
f1_keywords:
- C3269
helpviewer_keywords:
- C3269
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
ms.openlocfilehash: 041a0af061e4ddd1a691c396cdd15e86085124c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113689"
---
# <a name="compiler-error-c3269"></a>编译器错误 C3269

"function"：托管或 WinRTtype 的成员函数不能用 "..." 声明

托管和 WinRT 类成员函数不能声明可变长度的参数列表。

下面的示例将生成 C3269，并演示如何修复此错误：

```cpp
// C3269_2.cpp
// compile with: /clr

ref struct A
{
   void func(int i, ...)   // C3269
   // try the following line instead
   // void func(int i )
   {
   }
};

int main()
{
}
```
