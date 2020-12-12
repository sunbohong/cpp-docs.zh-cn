---
description: 了解详细信息： c + +/CLI 中的封送处理概述
title: C++ 中的封送处理概述
ms.date: 07/12/2019
ms.topic: reference
f1_keywords:
- marshaling
- marshalling
helpviewer_keywords:
- Visual C++, marshaling
- C++ Support Library, marshaling
- marshaling, about marshaling
ms.assetid: 997dd4bc-5f98-408f-b890-f35de9ce3bb8
ms.openlocfilehash: 35294a204d338087a609746e6ae2e5e07ea07b59
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255530"
---
# <a name="overview-of-marshaling-in-ccli"></a>C + +/CLI 中的封送概述

在混合模式下，有时必须将数据封送到本机类型和托管类型。 *封送处理库* 有助于以简单方式封送和转换数据。  封送处理库由一组函数和一个 `marshal_context` 为常见类型执行封送处理的类组成。 在 Visual Studio edition 的 **include/msclr** 目录的这些标头中定义该库：

|标头|描述|
|---------------|-----------------|
|marshal|`marshal_context` 类和无上下文封送处理函数|
|marshal_atl。h| 用于封送 ATL 类型的函数|
|marshal_cppstd。h|用于封送标准 c + + 类型的函数|
|marshal_windows。h|用于封送处理 Windows 类型的函数|

**Msclr** 文件夹的默认路径如下所示，具体取决于你拥有的版本和版本号：

```cmd
C:\\Program Files (x86)\\Microsoft Visual Studio\\Preview\\Enterprise\\VC\\Tools\\MSVC\\14.15.26528\\include\\msclr
```

可以使用带或不带 [Marshal_context 类](../dotnet/marshal-context-class.md)的封送处理库。 某些转换需要上下文。 其他转换可以使用 [marshal_as](../dotnet/marshal-as.md) 函数来实现。 下表列出了支持的当前转换、是否需要上下文以及必须包含的封送文件：

|从类型|到类型|Marshal 方法|包含文件|
|---------------|-------------|--------------------|------------------|
|System：： String ^|const char \*|marshal_context|marshal|
|const char \*|System：： String ^|marshal_as|marshal|
|char \*|System：： String ^|marshal_as|marshal|
|System：： String ^|const wchar_t\*|marshal_context|marshal|
|const wchar_t \*|System：： String ^|marshal_as|marshal|
|wchar_t \*|System：： String ^|marshal_as|marshal|
|System：： IntPtr|句柄|marshal_as|marshal_windows。h|
|句柄|System：： IntPtr|marshal_as|marshal_windows。h|
|System：： String ^|BSTR|marshal_context|marshal_windows。h|
|BSTR|System：： String ^|marshal_as|marshal|
|System：： String ^|bstr_t|marshal_as|marshal_windows。h|
|bstr_t|System：： String ^|marshal_as|marshal_windows。h|
|System：： String ^|std：： string|marshal_as|marshal_cppstd。h|
|std：： string|System：： String ^|marshal_as|marshal_cppstd。h|
|System：： String ^|std::wstring|marshal_as|marshal_cppstd。h|
|std::wstring|System：： String ^|marshal_as|marshal_cppstd。h|
|System：： String ^|CStringT\<char>|marshal_as|marshal_atl。h|
|CStringT\<char>|System：： String ^|marshal_as|marshal_atl。h|
|System：： String ^|CStringT<wchar_t>|marshal_as|marshal_atl。h|
|CStringT<wchar_t>|System：： String ^|marshal_as|marshal_atl。h|
|System：： String ^|CComBSTR|marshal_as|marshal_atl。h|
|CComBSTR|System：： String ^|marshal_as|marshal_atl。h|

仅当从托管到本机数据类型进行封送处理并且要转换到的本机类型没有自动清理的析构函数时，才需要使用上下文。 封送上下文会在其析构函数中销毁分配的本机数据类型。 因此，只在删除上下文之前，需要上下文的转换才有效。 若要保存任何封送的值，必须将这些值复制到您自己的变量中。

> [!NOTE]
> 如果你已 `NULL` 在字符串中嵌入了，则不保证封送处理字符串的结果。 嵌入的 `NULL` 可能会导致字符串被截断，或者它们可能会被保留。

此示例演示如何在 include 标头声明中包括 msclr 目录：

`#include "msclr\marshal_cppstd.h"`

可以扩展封送处理库，以便添加您自己的封送处理类型。 有关扩展封送处理库的详细信息，请参阅 [如何：扩展封送处理库](../dotnet/how-to-extend-the-marshaling-library.md)。

## <a name="see-also"></a>请参阅

[C + + 支持库](../dotnet/cpp-support-library.md)<br/>
[如何：扩展封送处理库](../dotnet/how-to-extend-the-marshaling-library.md)
