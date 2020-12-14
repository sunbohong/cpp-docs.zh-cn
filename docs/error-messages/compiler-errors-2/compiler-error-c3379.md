---
description: 了解更多：编译器错误 C3379
title: 编译器错误 C3379
ms.date: 11/04/2016
f1_keywords:
- C3379
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
ms.openlocfilehash: 622a1327eb84d83fa24d8a084e3266183c669120
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220729"
---
# <a name="compiler-error-c3379"></a>编译器错误 C3379

"class"：嵌套类不能将程序集访问说明符作为声明的一部分

当应用于托管类型（如类或结构）时， [public](../../cpp/public-cpp.md) 和 [private](../../cpp/private-cpp.md) 关键字指示是否通过程序集元数据公开此类。 `public` 或 `private` 不能应用于嵌套类，这将继承封闭类的程序集访问。

与 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)一起使用时， `ref` 和 `value` 关键字指示类被托管 (请参阅) 的 [类和结构](../../extensions/classes-and-structs-cpp-component-extensions.md) 。

下面的示例生成 C3379：

```cpp
// C3379a.cpp
// compile with: /clr
using namespace System;

public ref class A {
public:
   static int i = 9;

   public ref class BA {   // C3379
   // try the following line instead
   // ref class BA {
   public:
      static int ii = 8;
   };
};

int main() {

   A^ myA = gcnew A;
   Console::WriteLine(myA->i);

   A::BA^ myBA = gcnew A::BA;
   Console::WriteLine(myBA->ii);
}
```
