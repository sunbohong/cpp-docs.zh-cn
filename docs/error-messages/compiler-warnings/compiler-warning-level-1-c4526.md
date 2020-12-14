---
description: 了解详细信息：编译器警告 (等级 1) C4526
title: 编译器警告（等级 1）C4526
ms.date: 11/04/2016
f1_keywords:
- C4526
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
ms.openlocfilehash: 13eddea0fcf82686333fe51d253c3b24552e18c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294816"
---
# <a name="compiler-warning-level-1-c4526"></a>编译器警告（等级 1）C4526

"function"：静态成员函数不能重写虚函数 "virtual function'override 已忽略，虚函数将被隐藏

静态成员函数满足用于重写虚函数的条件，这使得成员函数成为虚函数和静态函数。

下面的代码生成 C4526：

```cpp
// C4526.cpp
// compile with: /W1 /c
// C4526 expected
struct myStruct1 {
   virtual void __stdcall func( int ) = 0;
};

struct myStruct2: public myStruct1 {
   static void __stdcall func( int );
};
```

下面是可能的修补程序：

- 如果函数旨在重写基类虚函数，则移除静态说明符。

- 如果函数旨在用作静态成员函数，请将其重命名，使其不会与基类虚函数冲突。
