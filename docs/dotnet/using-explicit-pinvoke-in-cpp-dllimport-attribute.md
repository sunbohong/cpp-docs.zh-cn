---
description: '了解详细信息：在 c + + 中使用显式 PInvoke (DllImport 特性) '
title: 在 C++ 中使用显式 PInvoke（DllImport 特性）
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling [C++], platform invoke
- C++ Interop, platform invoke
- interop [C++], platform invoke
- platform invoke [C++], marshaling in C++
- data marshaling [C++], platform invoke
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
ms.openlocfilehash: 6c49195cdb677474809435a5bd826808260680e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305457"
---
# <a name="using-explicit-pinvoke-in-c-dllimport-attribute"></a>在 C++ 中使用显式 PInvoke（DllImport 特性）

.NET Framework 提供了显式平台调用 (或 PInvoke) 功能，并提供了 `Dllimport` 特性，以允许托管应用程序调用在 dll 内打包的非托管函数。 如果非托管 Api 打包为 Dll 并且源代码不可用，则必须使用显式 PInvoke。 例如，调用 Win32 函数需要 PInvoke。 否则，请使用隐式 P {Invoke; 有关详细信息，请参阅 [使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md) 。

PInvoke 使用来工作 <xref:System.Runtime.InteropServices.DllImportAttribute> 。 此属性采用 DLL 的名称作为其第一个参数，位于将使用的每个 DLL 入口点的函数声明之前。 函数的签名必须与 DLL 导出的函数的名称相匹配 (但可以通过定义托管类型的声明隐式执行某些类型转换 `DllImport` 。 ) 

结果是每个本机 DLL 函数的托管入口点，其中包含所需的转换代码 (或 thunk) 和简单的数据转换。 然后，托管函数可以通过这些入口点调入 DLL。 将完全管理作为 PInvoke 的结果插入到模块中的代码。

## <a name="in-this-section"></a>本节内容

- [从托管代码调用本机函数](../dotnet/calling-native-functions-from-managed-code.md)

- [如何：使用 PInvoke 从托管代码调用本机 Dll](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)

- [如何：使用 PInvoke 封送字符串](../dotnet/how-to-marshal-strings-using-pinvoke.md)

- [如何：使用 PInvoke 封送结构](../dotnet/how-to-marshal-structures-using-pinvoke.md)

- [如何：使用 PInvoke 封送数组](../dotnet/how-to-marshal-arrays-using-pinvoke.md)

- [如何：使用 PInvoke 封送函数指针](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)

- [如何：使用 PInvoke 封送嵌入式指针](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)

## <a name="see-also"></a>请参阅

[从托管代码调用本机函数](../dotnet/calling-native-functions-from-managed-code.md)
