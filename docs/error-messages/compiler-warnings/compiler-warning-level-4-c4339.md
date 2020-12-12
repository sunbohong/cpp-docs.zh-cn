---
description: 详细了解：编译器警告 (级别 4) C4339
title: 编译器警告（等级 4）C4339
ms.date: 11/04/2016
f1_keywords:
- C4339
helpviewer_keywords:
- C4339
ms.assetid: 5b83353d-7777-4afb-8476-3c368349028c
ms.openlocfilehash: e05a7a73ac0cbbf056e5e30db0989e7fe933d01e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294517"
---
# <a name="compiler-warning-level-4-c4339"></a>编译器警告（等级 4）C4339

“type”: 在 WinRT 或 CLR 元数据中检测到使用了未定义的类型 - 使用此类型可能导致运行时异常

类型未在针对 Windows 运行时或公共语言运行时编译的代码中定义。 定义类型以避免可能的运行时异常。

默认情况下，此警告处于关闭状态。 请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 了解详细信息。

下面的示例将生成 C4339，并演示如何修复此错误：

```cpp
// C4339.cpp
// compile with: /W4 /clr /c
// C4339 expected
#pragma warning(default : 4339)

// Delete the following line to resolve.
class A;

// Uncomment the following line to resolve.
// class A{};

class X {
public:
   X() {}

   virtual A *mf() {
      return 0;
   }
};

X * f() {
   return new X();
}
```
