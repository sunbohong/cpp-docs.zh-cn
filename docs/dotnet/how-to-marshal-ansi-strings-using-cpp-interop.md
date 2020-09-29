---
title: 如何：使用 C++ 互操作封送 ANSI 字符串
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- ANSI [C++], marshaling strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
ms.assetid: 5eda2eb6-5140-40f0-82cf-7ce171fffb45
ms.openlocfilehash: 3bdffa761bef74b9956842122b913e8213c736e9
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414563"
---
# <a name="how-to-marshal-ansi-strings-using-c-interop"></a>如何：使用 C++ 互操作封送 ANSI 字符串

本主题演示如何使用 c + + 互操作来传递 ANSI 字符串，但 .NET Framework 以 <xref:System.String> Unicode 格式表示字符串，因此转换到 ANSI 是一个额外的步骤。 若要与其他字符串类型互操作，请参阅以下主题：

- [如何：使用 c + + 互操作封送 Unicode 字符串](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [如何：使用 c + + 互操作封送 COM 字符串](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

下面的代码示例使用 [托管的非托管](../preprocessor/managed-unmanaged.md) #pragma 指令来实现同一文件中的托管和非托管函数，但如果在单独的文件中定义，则这些函数将以相同的方式进行交互。 由于只包含非托管函数的文件不需要用 [/clr (公共语言运行时编译) ](../build/reference/clr-common-language-runtime-compilation.md)进行编译，因此它们可以保留它们的性能特征。

## <a name="example-pass-ansi-string"></a>示例：传递 ANSI 字符串

该示例演示如何使用将 ANSI 字符串从托管的传递到非托管函数 <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> 。 此方法在执行转换后，在非托管堆上分配内存并返回地址。 这意味着不需要进行固定 (因为 GC 堆上的内存未传递到非托管函数) 并且从返回的 IntPtr <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> 必须显式释放或内存泄漏结果。

```cpp
// MarshalANSI1.cpp
// compile with: /clr
#include <iostream>
#include <stdio.h>

using namespace std;
using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

void NativeTakesAString(const char* p) {
   printf_s("(native) received '%s'\n", p);
}

#pragma managed

int main() {
   String^ s = gcnew String("sample string");
   IntPtr ip = Marshal::StringToHGlobalAnsi(s);
   const char* str = static_cast<const char*>(ip.ToPointer());

   Console::WriteLine("(managed) passing string...");
   NativeTakesAString( str );

   Marshal::FreeHGlobal( ip );
}
```

## <a name="example-data-marshaling-required-to-access-ansi-string"></a>示例：访问 ANSI 字符串所需的数据封送处理

下面的示例演示了访问非托管函数调用的托管函数中的 ANSI 字符串所需的数据封送处理。 托管函数接收本机字符串时，可以直接使用该函数，也可以使用方法将其转换为托管字符串 <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> ，如下所示。

```cpp
// MarshalANSI2.cpp
// compile with: /clr
#include <iostream>
#include <vcclr.h>

using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed

void ManagedStringFunc(char* s) {
   String^ ms = Marshal::PtrToStringAnsi(static_cast<IntPtr>(s));
   Console::WriteLine("(managed): received '{0}'", ms);
}

#pragma unmanaged

void NativeProvidesAString() {
   cout << "(native) calling managed func...\n";
   ManagedStringFunc("test string");
}

#pragma managed

int main() {
   NativeProvidesAString();
}
```

## <a name="see-also"></a>另请参阅

[使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)
