---
description: 了解更多：本机和 .NET 互操作性
title: 本机和 .NET 的互操作性
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++]
- .NET Framework [C++], interoperability with Visual C++
- interoperability [C++], about .NET interoperability
- interop [C++], about .NET interoperability
- managed code [C++], interoperability
- native code [C++]
- interoperability [C++]
- MFC [C++], .NET integration
- unmanaged code interoperability [C++]
- Visual C++, interoperability
- native code [C++], .NET interoperatibility
ms.assetid: f3ec6c99-c745-4256-b95b-f1d12ba17a5a
ms.openlocfilehash: 0276c4401b56f453549cf31433cc6f558daf1c02
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255634"
---
# <a name="native-and-net-interoperability"></a>本机和 .NET 的互操作性

Visual C++ 支持互操作性功能，这些功能允许托管和非托管构造共存，甚至在同一文件中进行互操作。 其他 .NET 语言也支持此功能的一小部分（如 P/Invoke），但 Visual C++ 提供的大多数互操作性支持在其他语言中都不可用。

## <a name="in-this-section"></a>本节内容

[混合 (本机和托管) 程序集](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
描述用 [/clr (公共语言运行时编译 ](../build/reference/clr-common-language-runtime-compilation.md) 生成的程序集) 编译器选项，该选项包含托管和非托管功能。

[在 MFC 中使用 Windows 窗体用户控件](../dotnet/using-a-windows-form-user-control-in-mfc.md)<br/>
讨论如何使用 MFC Windows 窗体支持类在 MFC 应用程序中承载 Windows 窗体控件。

[从托管代码调用本机函数](../dotnet/calling-native-functions-from-managed-code.md)<br/>
介绍如何从 .NET 应用程序使用非 CLR Dll。
