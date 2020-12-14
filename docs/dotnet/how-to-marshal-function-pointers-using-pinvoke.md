---
description: 了解详细信息：如何：使用 PInvoke 封送函数指针
title: 如何：使用 PInvoke 封送函数指针
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- interop [C++], callbacks and delegates
- platform invoke [C++], callbacks and delegates
- marshaling [C++], callbacks and delegates
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
ms.openlocfilehash: bfe3f669cf023ed914bdccb3ae15ccafefbb49c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302577"
---
# <a name="how-to-marshal-function-pointers-using-pinvoke"></a>如何：使用 PInvoke 封送函数指针

本主题说明在使用 .NET Framework P/Invoke 功能与非托管函数进行互操作时，如何使用托管委托来代替函数指针。 但是，建议在) 可能的情况下，Visual C++ 程序员使用 c + + 互操作功能 (，因为 P/Invoke 提供的编译时错误报告很少，并且不是类型安全的，并且可能会单调地实现。 如果将非托管 API 打包为 DLL 并且源代码不可用，则 P/Invoke 是唯一的选择。 否则，请参阅以下主题：

- [使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)

- [如何：使用 c + + 互操作封送回调和委托](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

将函数指针作为参数的非托管 Api 可以从托管代码调用托管代码，而不是本机函数指针。 编译器会自动将委托作为函数指针封送到非托管函数，并插入必要的托管/非托管转换代码。

## <a name="example"></a>示例

下面的代码由一个非托管模块和一个托管模块组成。 非托管模块是一个 DLL，它定义了一个名为 TakesCallback 的函数，该函数接受函数指针。 此地址用于执行函数。

托管模块定义一个委托，该委托将作为函数指针封送到本机代码，并使用 <xref:System.Runtime.InteropServices.DllImportAttribute> 属性向托管代码公开本机 TakesCallback 函数。 在 main 函数中，创建委托的实例并将其传递给 TakesCallback 函数。 程序输出演示此函数由本机 TakesCallback 函数执行。

托管函数取消了托管委托的垃圾回收，以防止在本机函数执行时 .NET Framework 垃圾回收重新定位委托。

```cpp
// TraditionalDll5.cpp
// compile with: /LD /EHsc
#include <iostream>
#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   /* Declare an unmanaged function type that takes two int arguments
      Note the use of __stdcall for compatibility with managed code */
   typedef int (__stdcall *CALLBACK)(int);
   TRADITIONALDLL_API int TakesCallback(CALLBACK fp, int);
}

int TakesCallback(CALLBACK fp, int n) {
   printf_s("[unmanaged] got callback address, calling it...\n");
   return fp(n);
}
```

```cpp
// MarshalDelegate.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

public delegate int GetTheAnswerDelegate(int);
public value struct TraditionalDLL {
   [DllImport("TraditionalDLL5.dll")]
   static public int TakesCallback(GetTheAnswerDelegate^ pfn, int n);
};

int GetNumber(int n) {
   Console::WriteLine("[managed] callback!");
   static int x = 0;
   ++x;
   return x + n;
}

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);
   pin_ptr<GetTheAnswerDelegate^> pp = &fp;
   Console::WriteLine("[managed] sending delegate as callback...");

   int answer = TraditionalDLL::TakesCallback(fp, 42);
}
```

请注意，不会向托管代码公开使用传统 #include 指令的任何部分。 事实上，DLL 仅在运行时进行访问，因此 <xref:System.Runtime.InteropServices.DllImportAttribute> 在编译时不会检测通过导入的函数的问题。

## <a name="see-also"></a>请参阅

[在 c + + 中使用显式 PInvoke (DllImport 特性) ](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
