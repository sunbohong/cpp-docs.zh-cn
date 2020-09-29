---
title: 如何：使用 C++ 互操作封送 COM 字符串
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- COM [C++], marshaling strings
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
ms.openlocfilehash: 3113f0bd04fc8433dc4c7f443914fca9245a54f4
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414329"
---
# <a name="how-to-marshal-com-strings-using-c-interop"></a>如何：使用 C++ 互操作封送 COM 字符串

本主题演示了 BSTR 如何 (COM 编程中的基本字符串格式，) 可以从托管函数传递到非托管函数，反之亦然。 若要与其他字符串类型互操作，请参阅以下主题：

- [如何：使用 c + + 互操作封送 Unicode 字符串](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [如何：使用 c + + 互操作封送 ANSI 字符串](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

下面的代码示例使用 [托管的非托管](../preprocessor/managed-unmanaged.md) #pragma 指令来实现同一文件中的托管和非托管函数，但如果在单独的文件中定义，则这些函数将以相同的方式进行交互。 仅包含非托管函数的文件不需要用/clr 编译 [ (公共语言运行时编译) ](../build/reference/clr-common-language-runtime-compilation.md)。

## <a name="example-pass-bstr-from-managed-to-unmanaged-function"></a>示例：从托管到非托管函数传递 BSTR

下面的示例演示了如何使用 BSTR (COM 编程中使用的字符串格式) 可以从托管函数传递到非托管函数。 调用托管函数使用 <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> 获取 .Net system.string 内容的 BSTR 表示形式的地址。 此指针使用 [pin_ptr (c + +/cli) ](../extensions/pin-ptr-cpp-cli.md) 进行固定，以确保在执行非托管函数时，不会更改其物理地址。 在 [pin_ptr (c + +/cli) ](../extensions/pin-ptr-cpp-cli.md) 超出范围之前，禁止垃圾回收器移动内存。

```cpp
// MarshalBSTR1.cpp
// compile with: /clr
#define WINVER 0x0502
#define _AFXDLL
#include <afxwin.h>

#include <iostream>
using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

void NativeTakesAString(BSTR bstr) {
   printf_s("%S", bstr);
}

#pragma managed

int main() {
   String^ s = "test string";

   IntPtr ip = Marshal::StringToBSTR(s);
   BSTR bs = static_cast<BSTR>(ip.ToPointer());
   pin_ptr<BSTR> b = &bs;

   NativeTakesAString( bs );
   Marshal::FreeBSTR(ip);
}
```

## <a name="example-pass-bstr-from-unmanaged-to-managed-function"></a>示例：将 BSTR 从非托管函数传递到托管函数

下面的示例演示如何从非托管函数向托管函数传递 BSTR。 接收托管函数可以使用中的字符串作为 BSTR，或使用将 <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> 其转换为， <xref:System.String> 以便与其他托管函数一起使用。 由于表示 BSTR 的内存是在非托管堆上分配的，因此无需进行固定，因为非托管堆上没有垃圾回收。

```cpp
// MarshalBSTR2.cpp
// compile with: /clr
#define WINVER 0x0502
#define _AFXDLL
#include <afxwin.h>

#include <iostream>
using namespace std;

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed

void ManagedTakesAString(BSTR bstr) {
   String^ s = Marshal::PtrToStringBSTR(static_cast<IntPtr>(bstr));
   Console::WriteLine("(managed) convered BSTR to String: '{0}'", s);
}

#pragma unmanaged

void UnManagedFunc() {
   BSTR bs = SysAllocString(L"test string");
   printf_s("(unmanaged) passing BSTR to managed func...\n");
   ManagedTakesAString(bs);
}

#pragma managed

int main() {
   UnManagedFunc();
}
```

## <a name="see-also"></a>另请参阅

[使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)
