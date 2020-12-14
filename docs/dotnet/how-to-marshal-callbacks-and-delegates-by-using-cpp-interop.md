---
description: 了解详细信息：如何：使用 c + + 互操作封送回调和委托
title: 如何：使用 C++ 互操作封送回调和委托
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- C++ Interop, callbacks and delegates
- interop [C++], callbacks and delegates
- delegates [C++], marshaling
- marshaling [C++], callbacks and delegates
- callbacks [C++], marshaling
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
ms.openlocfilehash: 4f32c1918dc3896e43a0055245877ddf4d030ade
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258208"
---
# <a name="how-to-marshal-callbacks-and-delegates-by-using-c-interop"></a>如何：使用 C++ 互操作封送回调和委托

本主题演示如何使用 Visual C++ 在托管和非托管代码之间进行回调和委托的封送处理 () 。

下面的代码示例使用 [托管的非托管](../preprocessor/managed-unmanaged.md) #pragma 指令来实现同一文件中的托管和非托管函数，但也可以在单独的文件中定义函数。 不需要用 [/clr (公共语言运行时编译) ](../build/reference/clr-common-language-runtime-compilation.md)来编译只包含非托管函数的文件。

## <a name="example-configure-unmanaged-api-to-trigger-managed-delegate"></a>示例：将非托管 API 配置为触发托管委托

下面的示例演示如何将非托管 API 配置为触发托管委托。 将创建一个托管委托，并使用一个互操作方法 <xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A> 检索该委托的基础入口点。 然后，将此地址传递给非托管函数，该函数将调用它，而不知道它是作为托管函数实现的。

请注意，可以使用 [pin_ptr (c + +/cli) ](../extensions/pin-ptr-cpp-cli.md) 来固定委托，但这并不是必需的，以防止垃圾回收器重新定位或释放它。 需要防范过早的垃圾回收，但固定提供的保护比所需的更多，因为它会阻止回收，同时还会阻止重定位。

如果委托由垃圾回收重新定位，则它不会影响 underlaying 托管的回调，因此 <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> 用于添加对委托的引用，从而允许重定位委托，但阻止释放。 使用 GCHandle 而不是 pin_ptr 降低了托管堆的可能碎片。

```cpp
// MarshalDelegate1.cpp
// compile with: /clr
#include <iostream>

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

// Declare an unmanaged function type that takes two int arguments
// Note the use of __stdcall for compatibility with managed code
typedef int (__stdcall *ANSWERCB)(int, int);

int TakesCallback(ANSWERCB fp, int n, int m) {
   printf_s("[unmanaged] got callback address, calling it...\n");
   return fp(n, m);
}

#pragma managed

public delegate int GetTheAnswerDelegate(int, int);

int GetNumber(int n, int m) {
   Console::WriteLine("[managed] callback!");
   return n + m;
}

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);
   GCHandle gch = GCHandle::Alloc(fp);
   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());
   Console::WriteLine("[managed] sending delegate as callback...");

// force garbage collection cycle to prove
// that the delegate doesn't get disposed
   GC::Collect();

   int answer = TakesCallback(cb, 243, 257);

// release reference to delegate
   gch.Free();
}
```

## <a name="example-function-pointer-stored-by-unmanaged-api"></a>示例：非托管 API 存储的函数指针

下面的示例与前面的示例类似，但在这种情况下，提供的函数指针由非托管 API 存储，因此可以随时调用它，要求在任意长度的时间内抑制垃圾回收。 因此，下面的示例使用的全局实例 <xref:System.Runtime.InteropServices.GCHandle> 来防止重定位委托，而与函数范围无关。 如第一个示例中所述，在这些示例中不需要使用 pin_ptr，但在这种情况下，因为 pin_ptr 的作用域仅限于单个函数。

```cpp
// MarshalDelegate2.cpp
// compile with: /clr
#include <iostream>

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

// Declare an unmanaged function type that takes two int arguments
// Note the use of __stdcall for compatibility with managed code
typedef int (__stdcall *ANSWERCB)(int, int);
static ANSWERCB cb;

int TakesCallback(ANSWERCB fp, int n, int m) {
   cb = fp;
   if (cb) {
      printf_s("[unmanaged] got callback address (%d), calling it...\n", cb);
      return cb(n, m);
   }
   printf_s("[unmanaged] unregistering callback");
   return 0;
}

#pragma managed

public delegate int GetTheAnswerDelegate(int, int);

int GetNumber(int n, int m) {
   Console::WriteLine("[managed] callback!");
   static int x = 0;
   ++x;

   return n + m + x;
}

static GCHandle gch;

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);

   gch = GCHandle::Alloc(fp);

   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());
   Console::WriteLine("[managed] sending delegate as callback...");

   int answer = TakesCallback(cb, 243, 257);

   // possibly much later (in another function)...

   Console::WriteLine("[managed] releasing callback mechanisms...");
   TakesCallback(0, 243, 257);
   gch.Free();
}
```

## <a name="see-also"></a>请参阅

[使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)
