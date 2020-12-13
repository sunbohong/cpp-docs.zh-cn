---
description: 了解更多：编译器错误 C3380
title: 编译器错误 C3380
ms.date: 11/04/2016
f1_keywords:
- C3380
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
ms.openlocfilehash: bb633d75d08fdbb902f086b3a4cd6a8a6db1fc69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334989"
---
# <a name="compiler-error-c3380"></a>编译器错误 C3380

“class”: 程序集访问说明符无效 - 只允许“public”或“private”

应用于托管类或结构时， [public](../../cpp/public-cpp.md) 和 [private](../../cpp/private-cpp.md) 关键字指示是否通过程序集元数据公开此类。 程序中使用 `public` /clr `private` 编译的类只可使用 [或](../../build/reference/clr-common-language-runtime-compilation.md)。

`ref`和 `value` 关键字与[/clr](../../build/reference/clr-common-language-runtime-compilation.md)一起使用时指示类是托管的 (参阅) 的[类和结构](../../extensions/classes-and-structs-cpp-component-extensions.md)。

以下示例生成 C3380：

```cpp
// C3380_2.cpp
// compile with: /clr
protected ref class A {   // C3380
// try the following line instead
// ref class A {
public:
   static int i = 9;
};

int main() {
   A^ myA = gcnew A;
   System::Console::WriteLine(myA->i);
}
```
