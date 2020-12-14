---
description: 了解详细信息：如何：使用 PInvoke 封送数组
title: 如何：使用 PInvoke 封送数组
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling [C++], arrays
- platform invoke [C++], arrays
- interop [C++], arrays
- data marshaling [C++], arrays
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
ms.openlocfilehash: 90fd7b2cbefe2fb3621f512d49fbc088240922a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258214"
---
# <a name="how-to-marshal-arrays-using-pinvoke"></a>如何：使用 PInvoke 封送数组

本主题说明如何使用 CLR 字符串类型（ <xref:System.String> .NET Framework 平台调用支持）来调用接受 C 样式字符串的本机函数。 建议在可能的情况下，建议使用 c + + 互操作功能 () ，因为 P/Invoke 提供的编译时错误报告很少，并且不是类型安全的，并且在实现时可能单调乏味。 Visual C++ 如果将非托管 API 打包为 DLL 并且源代码不可用，则仅 (使用 P/Invoke 选项，否则请参阅 [使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)) 。

## <a name="example"></a>示例

因为本机和托管数组在内存中布局不同，所以跨托管/非托管边界成功传递它们需要转换或封送处理。 本主题演示如何将简单 (blitable) 项的数组从托管代码传递到本机函数。

与通常情况下的托管/非托管数据封送处理一样， <xref:System.Runtime.InteropServices.DllImportAttribute> 特性用于为将使用的每个本机函数创建托管入口点。 对于采用数组作为参数的函数， <xref:System.Runtime.InteropServices.MarshalAsAttribute> 还必须使用特性来指定编译器如何封送数据。 在下面的示例中， <xref:System.Runtime.InteropServices.UnmanagedType> 枚举用于指示托管数组将作为 C 样式数组封送。

下面的代码由一个非托管模块和一个托管模块组成。 非托管模块是一个 DLL，它定义接受整数数组的函数。 第二个模块是一种托管的命令行应用程序，它可导入此函数，但会根据托管数组进行定义，并使用 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性来指定在调用时应将数组转换为本机数组。

用/clr 编译托管模块

```cpp
// TraditionalDll4.cpp
// compile with: /LD /EHsc
#include <iostream>

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   TRADITIONALDLL_API void TakesAnArray(int len, int[]);
}

void TakesAnArray(int len, int a[]) {
   printf_s("[unmanaged]\n");
   for (int i=0; i<len; i++)
      printf("%d = %d\n", i, a[i]);
}
```

```cpp
// MarshalBlitArray.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value struct TraditionalDLL {
   [DllImport("TraditionalDLL4.dll")]
   static public void TakesAnArray(
   int len,[MarshalAs(UnmanagedType::LPArray)]array<int>^);
};

int main() {
   array<int>^ b = gcnew array<int>(3);
   b[0] = 11;
   b[1] = 33;
   b[2] = 55;
   TraditionalDLL::TakesAnArray(3, b);

   Console::WriteLine("[managed]");
   for (int i=0; i<3; i++)
      Console::WriteLine("{0} = {1}", i, b[i]);
}
```

请注意，DLL 的任何部分都不会通过传统的 #include 指令公开给托管代码。 事实上，由于 DLL 仅在运行时进行访问，因此 <xref:System.Runtime.InteropServices.DllImportAttribute> 在编译时不会检测用导入的函数的问题。

## <a name="see-also"></a>请参阅

[在 c + + 中使用显式 PInvoke (DllImport 特性) ](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
