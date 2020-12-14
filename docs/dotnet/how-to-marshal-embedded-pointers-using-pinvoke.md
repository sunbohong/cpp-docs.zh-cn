---
description: 了解详细信息：如何：使用 PInvoke 封送嵌入式指针
title: 如何：使用 PInvoke 封送嵌入式指针
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- embedded pointers [C++]
- interop [C++], embedded pointers
- platform invoke [C++], embedded pointers
- marshaling [C++], embedded pointers
- data marshaling [C++], embedded pointers
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
ms.openlocfilehash: d31660a9a8ba345b380d442bb4484e332fe9d7cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302551"
---
# <a name="how-to-marshal-embedded-pointers-using-pinvoke"></a>如何：使用 PInvoke 封送嵌入式指针

在非托管 Dll 中实现的函数可以使用平台调用 (P/Invoke) 功能从托管代码调用。 如果 DLL 的源代码不可用，则 P/Invoke 是用于互操作的唯一选项。 但是，与其他 .NET 语言不同，Visual C++ 提供了 P/Invoke 的替代方法。 有关详细信息，请参阅 [使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md) 和 [如何：使用 c + + 互操作封送嵌入式指针](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)。

## <a name="example"></a>示例

如果将结构传递给本机代码，则会要求创建一个等效于将数据布局作为本地结构的托管结构。 但是，包含指针的结构需要特殊处理。 对于本机结构中的每个嵌入指针，结构的托管版本应包含类型的实例 <xref:System.IntPtr> 。 此外，必须使用 <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A> 、和方法显式分配、初始化和释放这些实例的内存 <xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A> <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> 。

下面的代码由一个非托管模块和一个托管模块组成。 非托管模块是一个 DLL，它定义了一个函数，该函数接受一个名为 ListString 的结构，该结构包含一个指针和一个名为 TakesListStruct 的函数。 托管模块是一个命令行应用程序，该应用程序导入 TakesListStruct 函数并定义一个名为 MListStruct 的结构，该结构等效于本机 ListStruct，只不过 double * 表示为 <xref:System.IntPtr> 实例。 在调用 TakesListStruct 之前，main 函数将分配并初始化此字段引用的内存。

```cpp
// TraditionalDll6.cpp
// compile with: /EHsc /LD
#include <stdio.h>
#include <iostream>
#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

#pragma pack(push, 8)
struct ListStruct {
   int count;
   double* item;
};
#pragma pack(pop)

extern "C" {
   TRADITIONALDLL_API void TakesListStruct(ListStruct);
}

void TakesListStruct(ListStruct list) {
   printf_s("[unmanaged] count = %d\n", list.count);
   for (int i=0; i<list.count; i++)
      printf_s("array[%d] = %f\n", i, list.item[i]);
}
```

```cpp
// EmbeddedPointerMarshalling.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[StructLayout(LayoutKind::Sequential, Pack=8)]
value struct MListStruct {
   int count;
   IntPtr item;
};

value struct TraditionalDLL {
    [DllImport("TraditionalDLL6.dll")]
   static public void TakesListStruct(MListStruct);
};

int main() {
   array<double>^ parray = gcnew array<double>(10);
   Console::WriteLine("[managed] count = {0}", parray->Length);

   Random^ r = gcnew Random();
   for (int i=0; i<parray->Length; i++) {
      parray[i] = r->NextDouble() * 100.0;
      Console::WriteLine("array[{0}] = {1}", i, parray[i]);
   }

   int size = Marshal::SizeOf(double::typeid);
   MListStruct list;
   list.count = parray->Length;
   list.item = Marshal::AllocCoTaskMem(size * parray->Length);

   for (int i=0; i<parray->Length; i++) {
      IntPtr t = IntPtr(list.item.ToInt32() + i * size);
      Marshal::StructureToPtr(parray[i], t, false);
   }

   TraditionalDLL::TakesListStruct( list );
   Marshal::FreeCoTaskMem(list.item);
}
```

请注意，不会向托管代码公开使用传统 #include 指令的任何部分。 事实上，DLL 仅在运行时进行访问，因此 <xref:System.Runtime.InteropServices.DllImportAttribute> 在编译时不会检测通过导入的函数的问题。

## <a name="see-also"></a>请参阅

[在 c + + 中使用显式 PInvoke (DllImport 特性) ](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
