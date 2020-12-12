---
description: '了解详细信息：互操作 (c + + 的性能注意事项) '
title: 互操作的性能注意事项 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- /clr compiler option [C++], interop performance considerations
- platform invoke [C++], interoperability
- interop [C++], performance consideraitons
- mixed assemblies [C++], performance considerations
- interoperability [C++], performance considerations
ms.assetid: bb9a282e-c3f8-40eb-a2fa-45d80d578932
ms.openlocfilehash: 29723f0ea5c7b745100ab4c7abb7f59abce47db6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255555"
---
# <a name="performance-considerations-for-interop-c"></a>互操作的性能注意事项 (C++)

本主题提供了一些准则，用于降低托管/非托管互操作转换对运行时性能的影响。

Visual C++ 支持与其他 .NET 语言（如 Visual Basic 和 c # (P/Invoke) ）相同的互操作机制，但它还提供了特定于 Visual C++ (c + + 互操作) 的互操作支持。 对于性能关键的应用程序，了解每种互操作技术的性能含义非常重要。

无论使用何种互操作技术，当托管函数每次调用非托管函数时，都需要特殊的转换序列（称为 thunk），反之亦然。 Microsoft c + + 编译器会自动插入这些 thunk，但请务必注意，这些转换在性能方面的代价很高。

## <a name="reducing-transitions"></a>减少转换

避免或降低互操作 thunk 的成本的一种方法是重构所涉及的接口，以最大程度地减少托管/非托管转换。 通过面向常用的接口（涉及跨托管/非托管边界频繁调用的接口），可以显著提高性能。 例如，在紧凑循环中调用非托管函数的托管函数是一种很好的重构候选项。 如果循环本身被移到非托管端，或创建了非托管调用的托管替代项 (可能在托管端上对数据进行排队，然后在循环) 之后同时将数据封送到非托管 API，则可以显著减少转换数量。

## <a name="pinvoke-vs-c-interop"></a>P/Invoke 与 c + + 互操作

对于 .NET 语言（如 Visual Basic 和 c #），与本机组件互操作的指定方法是 P/Invoke。 由于 .NET Framework 支持 P/Invoke，Visual C++ 也支持它，但 Visual C++ 还提供了其自己的互操作性支持，称为 c + + 互操作。 C + + 互操作优于 P/Invoke，因为 P/Invoke 不是类型安全的。 因此，错误主要在运行时报告，但在 P/Invoke 上，c + + 互操作也具有性能优势。

每当托管函数调用非托管函数时，这两种方法都需要执行几项操作：

- 函数调用参数从 CLR 封送到本机类型。

- 执行托管到非托管的 thunk。

- 使用) 的本机版本参数 (调用非托管函数。

- 执行非托管到托管的 thunk。

- 返回类型以及任何 "out" 或 "in，out" 参数都是从本机类型封送到 CLR 类型。

托管/非托管 thunk 对于互操作都是必需的，但需要的数据封送处理取决于所涉及的数据类型、函数签名以及数据的使用方式。

C + + 互操作执行的数据封送处理是最简单的形式：仅以按位方式在托管/非托管边界内复制参数;根本不执行任何转换。 对于 P/Invoke，如果所有参数都是简单的、可直接复制的类型，则此值为 true。 否则，P/Invoke 会执行非常可靠的步骤，将每个托管参数转换为适当的本机类型，反之亦然，如果参数标记为 "out" 或 "in，out"。

换言之，c + + 互操作使用最快的数据封送方法，而 P/Invoke 使用最可靠的方法。 这意味着 c + + 互操作 (采用 c +) + 的典型方式，默认情况下，程序员负责解决此行为不安全或不适合的情况。

因此，c + + 互操作要求必须显式提供数据封送处理，但优点在于，程序员可以根据数据的性质和使用方式，随意决定适当的内容。 此外，尽管 P/Invoke 数据封送处理的行为可在自定义时修改，但 c + + 互操作允许按调用自定义数据封送处理。 P/Invoke 无法实现这一点。

有关 c + + 互操作的详细信息，请参阅 [使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)。

## <a name="see-also"></a>请参阅

[混合 (本机和托管) 程序集](../dotnet/mixed-native-and-managed-assemblies.md)
