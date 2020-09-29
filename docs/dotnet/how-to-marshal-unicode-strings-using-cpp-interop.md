---
title: 如何：使用 C++ 互操作封送 Unicode 字符串
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- Unicode, marshaling strings
ms.assetid: 96c2141d-6c5d-43ef-a1aa-5785afb9a9aa
ms.openlocfilehash: da320dbd41e7158e3bc2482b96a73c1f4728a01b
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414303"
---
# <a name="how-to-marshal-unicode-strings-using-c-interop"></a>如何：使用 C++ 互操作封送 Unicode 字符串

本主题演示 Visual C++ 互操作性的一小层面。 有关详细信息，请参阅 [使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)。

下面的代码示例使用 [托管的非托管](../preprocessor/managed-unmanaged.md) #pragma 指令来实现同一文件中的托管和非托管函数，但如果在单独的文件中定义，则这些函数将以相同的方式进行交互。 仅包含非托管函数的文件不需要用/clr 编译 [ (公共语言运行时编译) ](../build/reference/clr-common-language-runtime-compilation.md)。

本主题演示如何将 Unicode 字符串从托管函数传递到非托管函数，反之亦然。 若要与其他字符串类型互操作，请参阅以下主题：

- [如何：使用 c + + 互操作封送 ANSI 字符串](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [如何：使用 c + + 互操作封送 COM 字符串](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

## <a name="example-pass-unicode-string-from-managed-to-unmanaged-function"></a>示例：将 Unicode 字符串从托管函数传递到非托管函数

若要将 Unicode 字符串从托管函数传递到非托管函数，可以使用 Vcclr) 中 (声明的 PtrToStringChars 函数来访问存储托管字符串的内存。 由于此地址将传递给本机函数，因此，内存必须固定 [pin_ptr (c + +/cli) ](../extensions/pin-ptr-cpp-cli.md) ，以便在执行非托管函数时，如果发生垃圾回收循环，则会发生垃圾回收循环，这一点很重要。

```cpp
// MarshalUnicode1.cpp
// compile with: /clr
#include <iostream>
#include <stdio.h>
#include <vcclr.h>

using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

void NativeTakesAString(const wchar_t* p) {
   printf_s("(native) received '%S'\n", p);
}

#pragma managed

int main() {
   String^ s = gcnew String("test string");
   pin_ptr<const wchar_t> str = PtrToStringChars(s);

   Console::WriteLine("(managed) passing string to native func...");
   NativeTakesAString( str );
}
```

## <a name="example-data-marshaling-required-to-access-unicode-string"></a>示例：访问 Unicode 字符串所需的数据封送处理

下面的示例演示了在非托管函数调用的托管函数中访问 Unicode 字符串所需的数据封送处理。 托管函数接收本机 Unicode 字符串后，使用方法将其转换为托管字符串 <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> 。

```cpp
// MarshalUnicode2.cpp
// compile with: /clr
#include <iostream>

using namespace std;
using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed

void ManagedStringFunc(wchar_t* s) {
   String^ ms = Marshal::PtrToStringUni((IntPtr)s);
   Console::WriteLine("(managed) received '{0}'", ms);
}

#pragma unmanaged

void NativeProvidesAString() {
   cout << "(unmanaged) calling managed func...\n";
   ManagedStringFunc(L"test string");
}

#pragma managed

int main() {
   NativeProvidesAString();
}
```

## <a name="see-also"></a>另请参阅

[使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)
