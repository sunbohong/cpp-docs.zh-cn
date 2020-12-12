---
description: 了解更多：编译器错误 C3894
title: 编译器错误 C3894
ms.date: 11/04/2016
f1_keywords:
- C3894
helpviewer_keywords:
- C3894
ms.assetid: 6d5ac903-1dea-431d-8e3a-cebca4342983
ms.openlocfilehash: 6290cb247e45c4bd3fd3b140f467d608203b488b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115776"
---
# <a name="compiler-error-c3894"></a>编译器错误 C3894

"var"： initonly 静态数据成员的左值只允许在类 "class" 的类构造函数中使用

静态 [initonly](../../dotnet/initonly-cpp-cli.md) 数据成员仅可在其声明或静态构造函数中用作左值。

实例 (非静态) initonly 数据成员只能用作其声明点上的左值，或者在 (非静态) 构造函数的实例中使用。

下面的示例生成 C3894：

```cpp
// C3894.cpp
// compile with: /clr
ref struct Y1 {
   initonly static int data_var = 0;

public:
   // class constructor
   static Y1() {
      data_var = 99;   // OK
      System::Console::WriteLine("in static constructor");
   }

   // not the class constructor
   Y1(int i) {
      data_var = i;   // C3894
   }

   static void Test() {}

};

int main() {
   Y1::data_var = 88;   // C3894
   int i = Y1::data_var;
   Y1 ^ MyY1 = gcnew Y1(99);
   Y1::Test();
}
```
