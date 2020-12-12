---
description: '了解详细信息：使用 c + + 互操作 (隐式 PInvoke) '
title: 使用 C++ 互操作（隐式 PInvoke）
ms.date: 11/04/2016
helpviewer_keywords:
- blittable types [C++]
- platform invoke [C++], implicit
- interop [C++], features
- data marshaling [C++], C++ Interop features
- porting [C++], C++ native to .NET
- COM interfaces [C++]
- implicit platform invoke
- examples [C++], interoperability
- types [C++], blittable
- marshaling [C++], C++ Interop features
- platform invoke [C++], examples
- interoperability [C++]
- C++ Interop
- interoperability [C++], Implicit PInvoke
- C++, interop
- C++ COM Interop
- .NET [C++], porting C++ native to
ms.assetid: 5f710bf1-88ae-4c4e-8326-b3f0b7c4c68a
ms.openlocfilehash: e2b1f1aeef68fd6329ef04a53249d7dce627f2c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255543"
---
# <a name="using-c-interop-implicit-pinvoke"></a>使用 C++ 互操作（隐式 PInvoke）

与其他 .NET 语言不同，Visual C++ 具有互操作性支持，允许托管和非托管代码存在于同一应用程序中，甚至在同一文件中， (与 [托管的非托管](../preprocessor/managed-unmanaged.md) 杂注) 相同。 这允许 Visual C++ 开发人员将 .NET 功能集成到现有 Visual C++ 应用程序中，而不会影响应用程序的其余部分。

你还可以使用 [dllexport，dllimport](../cpp/dllexport-dllimport.md)从托管编译单位调用非托管函数。

当你不需要指定将如何封送处理函数参数或在显式调用 DllImportAttribute 时可以指定的任何其他详细信息时，隐式 PInvoke 非常有用。

Visual C++ 提供了两种方法来使托管和非托管函数互操作：

- [在 c + + 中使用显式 PInvoke (DllImport 特性) ](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

.NET Framework 支持显式 PInvoke，它在大多数 .NET 语言中可用。 但顾名思义，c + + 互操作特定于 Visual C++。

## <a name="c-interop"></a>C++ 互操作

C + + 互操作提供更好的类型安全性，实现起来通常不太繁琐。 但是，如果非托管源代码不可用或跨平台项目，则不能使用 c + + 互操作。

## <a name="c-com-interop"></a>C++ COM 互操作

与 COM 组件互操作时，Visual C++ 支持的互操作性功能在其他 .NET 语言方面提供了特别的优势。 C + + 互操作允许同时访问 COM 组件，而不是限制 .NET Framework [Tlbimp.exe (类型库导) 入 ](/dotnet/framework/tools/tlbimp-exe-type-library-importer)程序的限制（如对数据类型的限制和对每个 com 接口的每个成员的强制公开）的限制，并且不需要单独的互操作程序集。 与 Visual Basic 和 c # 不同，Visual C++ 可以使用常用的 COM (机制（如 **CoCreateInstance** 和 **QueryInterface**) ）直接使用 com 对象。 这是可能的，因为 c + + 互操作功能导致编译器自动插入转换代码以从托管函数移动到非托管函数并再次返回。

使用 c + + 互操作时，COM 组件可以像平常一样使用，也可以包装在 c + + 类中。 这些包装类称为自定义运行时可调用包装器或 CRCWs，它们具有两个优于直接在应用程序代码中使用 COM 的优点：

- 生成的类可用于除 Visual C++ 以外的其他语言。

- 可以从托管客户端代码中隐藏 COM 接口的详细信息。 .NET 数据类型可用于替代本机类型，数据封送的详细信息可在 CRCW 中透明地执行。

无论是直接使用 COM 还是通过 CRCW 使用 COM，都必须封送非简单类型的自变量类型。

## <a name="blittable-types"></a>直接类型

对于使用简单的内部类型 (的非托管 Api，) 可 [直接复制和非直接复制到本机类型](/dotnet/framework/interop/blittable-and-non-blittable-types) ，不需要特殊编码，因为这些数据类型在内存中具有相同的表示形式，但更复杂的数据类型需要显式数据封送处理。 有关示例，请参阅 [如何：使用 PInvoke 从托管代码调用本机 dll](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)。

## <a name="example"></a>示例

```cpp
// vcmcppv2_impl_dllimp.cpp
// compile with: /clr:pure user32.lib
using namespace System::Runtime::InteropServices;

// Implicit DLLImport specifying calling convention
extern "C" int __stdcall MessageBeep(int);

// explicit DLLImport needed here to use P/Invoke marshalling because
// System::String ^ is not the type of the first parameter to printf
[DllImport("msvcrt.dll", EntryPoint = "printf", CallingConvention = CallingConvention::Cdecl,  CharSet = CharSet::Ansi)]
// or just
// [DllImport("msvcrt.dll")]
int printf(System::String ^, ...);

int main() {
   // (string literals are System::String by default)
   printf("Begin beep\n");
   MessageBeep(100000);
   printf("Done\n");
}
```

```Output
Begin beep
Done
```

## <a name="in-this-section"></a>本节内容

- [如何：使用 c + + 互操作封送 ANSI 字符串](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [如何：使用 c + + 互操作封送 Unicode 字符串](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [如何：使用 c + + 互操作封送 COM 字符串](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

- [如何：使用 c + + 互操作封送结构](../dotnet/how-to-marshal-structures-using-cpp-interop.md)

- [如何：使用 c + + 互操作封送数组](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)

- [如何：使用 c + + 互操作封送回调和委托](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

- [如何：使用 c + + 互操作封送嵌入式指针](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)

- [如何：访问 System：： String 中的字符](../dotnet/how-to-access-characters-in-a-system-string.md)

- [如何：将 char * 字符串转换为 System：： Byte 数组](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)

- [如何：将 System：： String 转换为 wchar_t * 或 char\*](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)

- [如何：将 System：： String 转换为标准字符串](../dotnet/how-to-convert-system-string-to-standard-string.md)

- [如何：将标准字符串转换为 System：： String](../dotnet/how-to-convert-standard-string-to-system-string.md)

- [如何：获取指向字节数组的指针](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)

- [如何：将非托管资源加载到字节数组中](../dotnet/how-to-load-unmanaged-resources-into-a-byte-array.md)

- [如何：修改本机函数中的引用类](../dotnet/how-to-modify-reference-class-in-a-native-function.md)

- [如何：确定映像为本机映像还是 CLR 映像](../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)

- [如何：向全局程序集缓存添加本机 DLL](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)

- [如何：在本机类型中保存对值类型的引用](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)

- [如何：在非托管内存中保存对象引用](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)

- [如何：检测/clr 编译](../dotnet/how-to-detect-clr-compilation.md)

- [如何：在 System：： Guid 和 _GUID 之间转换](../dotnet/how-to-convert-between-system-guid-and-guid.md)

- [如何：指定 out 参数](../dotnet/how-to-specify-an-out-parameter.md)

- [如何：在/clr 编译中使用本机类型](../dotnet/how-to-use-a-native-type-in-a-clr-compilation.md)

- [如何：在本机类型中声明句柄](../dotnet/how-to-declare-handles-in-native-types.md)

- [如何：包装本机类以供 C 使用#](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

有关在互操作方案中使用委托的信息，请参阅 [) 的委托 (c + + 组件扩展 ](../extensions/delegate-cpp-component-extensions.md)。

## <a name="see-also"></a>请参阅

- [从托管代码调用本机函数](../dotnet/calling-native-functions-from-managed-code.md)
