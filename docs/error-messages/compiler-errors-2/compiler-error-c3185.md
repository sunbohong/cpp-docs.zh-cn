---
description: 了解更多：编译器错误 C3185
title: 编译器错误 C3185
ms.date: 11/04/2016
f1_keywords:
- C3185
helpviewer_keywords:
- C3185
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
ms.openlocfilehash: 7dbcf11aa7c88d883aeccc8325832849f8b7a238
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242010"
---
# <a name="compiler-error-c3185"></a>编译器错误 C3185

在托管或 WinRT 类型“type”上使用了“typeid”，请改用“operator”

不能将 [typeid](../../cpp/typeid-operator.md) 运算符应用于托管或 WinRT 类型;请改用 [typeid](../../extensions/typeid-cpp-component-extensions.md) 。

下面的示例生成 C3185，并演示如何修复此错误：

```cpp
// C3185a.cpp
// compile with: /clr
ref class Base {};
ref class Derived : public Base {};

int main() {
   Derived ^ pd = gcnew Derived;
   Base ^pb = pd;
   const type_info & t1 = typeid(pb);   // C3185
   System::Type ^ MyType = Base::typeid;   // OK
};
```
