---
description: 了解更多：编译器错误 C3642
title: 编译器错误 C3642
ms.date: 11/04/2016
f1_keywords:
- C3642
helpviewer_keywords:
- C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
ms.openlocfilehash: 77d65d2bb2c426fe78671328b0eccab739b9dabe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340302"
---
# <a name="compiler-error-c3642"></a>编译器错误 C3642

"return_type/args"：无法从本机代码调用具有 __clrcall 调用约定的函数

无法从本机 (非托管) 代码中调用标记为 [__clrcall](../../cpp/clrcall.md) 调用约定的函数。

*return_type/args* 是函数的名称或要尝试调用的函数的类型 `__clrcall` 。  当你通过函数指针调用时，会使用类型。

若要从本机上下文调用托管函数，可以添加一个 "包装" 函数，该函数将调用 `__clrcall` 函数。 或者，可以使用 CLR 封送机制;有关详细信息，请参阅 [如何：使用 PInvoke 封送函数指针](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md) 。

下面的示例生成 C3642：

```cpp
// C3642.cpp
// compile with: /clr
using namespace System;
struct S {
   void Test(String ^ s) {   // CLR type in signature, implicitly __clrcall
      Console::WriteLine(s);
   }
   void Test2(char * s) {
      Test(gcnew String(s));
   }
};

#pragma unmanaged
int main() {
   S s;
   s.Test("abc");   // C3642
   s.Test2("abc");   // OK
}
```
