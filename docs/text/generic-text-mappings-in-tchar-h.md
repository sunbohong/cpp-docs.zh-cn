---
description: 了解详细信息 Generic-Text： tchar 中的映射
title: Tchar 中的 Generic-Text 映射
ms.date: 11/04/2016
helpviewer_keywords:
- mapping generic-text
- generic-text mappings [C++]
- character sets [C++], generic-text mappings
- Unicode [C++], generic-text mappings
- MBCS [C++], generic-text mappings
- TCHAR.H data types, mapping
- mappings [C++], TCHAR.H
ms.assetid: 01e1bb74-5a01-4093-8720-68b6c1fdda80
ms.openlocfilehash: f083dc03eab7db25b54955d8d34a13f2b5b7197b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118343"
---
# <a name="generic-text-mappings-in-tcharh"></a>Tchar 中的 Generic-Text 映射

为了简化代码的传输以实现国际用途，Microsoft 运行时库为许多数据类型、例程和其他对象提供了特定于 Microsoft 的一般文本映射。 您可以使用 tchar 中定义的这些映射来编写可以为单字节、多字节或 Unicode 字符集编译的泛型代码，具体取决于使用语句定义的清单常量 `#define` 。 一般文本映射是与 ANSI 不兼容的 Microsoft 扩展。

通过使用 tchar，你可以从相同源构建单字节、多字节字符集 (MBCS) 和 Unicode 应用程序。 tchar 定义了宏 (，其前缀 `_tcs`) 使用正确的预处理器定义，相应地映射到 `str` 、 `_mbs` 或 `wcs` 函数。 若要生成 MBCS，请定义符号 `_MBCS` 。 若要生成 Unicode，请定义符号 `_UNICODE` 。 若要生成单字节应用程序，请不 (默认) 中定义。 默认情况下， `_UNICODE` 为 MFC 应用程序定义。

`_TCHAR`数据类型在 tchar 中有条件地定义。 如果为 `_UNICODE` 您的生成定义了符号， `_TCHAR` 则将定义为 **`wchar_t`** ; 否则，对于单字节和 MBCS 生成，它定义为 **`char`** 。  (**`wchar_t`** ，基本的 Unicode 宽字符数据类型是8位的16位对应项 **`signed char`** 。 ) 对于国际化应用程序，请使用 `_tcs` 以单元而非字节方式运行的函数系列 `_TCHAR` 。 例如， `_tcsncpy` 副本 `n` `_TCHARs` ，而不是 `n` 字节。

由于某些单字节字符集 (SBCS) 字符串处理函数采用 (签名) **`char*`** 参数，定义时编译器警告结果类型不匹配 `_MBCS` 。 可以通过三种方法来避免此警告：

1. 在 tchar 中使用类型安全内联函数 thunk。 这是默认行为。

1. 通过在命令行上定义，使用 tchar 中的直接宏 `_MB_MAP_DIRECT` 。 如果执行此操作，必须手动匹配类型。 这是最快的方法，但不是类型安全的方法。

1. 在 tchar 中使用类型安全的静态链接库函数 thunk。 为此，在命令行上定义常量 `_NO_INLINING`。 这是最慢的方法，但是最能确保类型安全。

### <a name="preprocessor-directives-for-generic-text-mappings"></a>用于一般文本映射的预处理器指令

|# define|编译的版本|示例|
|---------------|----------------------|-------------|
|`_UNICODE`|Unicode（宽字符）|`_tcsrev` 映射到 `_wcsrev`|
|`_MBCS`|多字节字符|`_tcsrev` 映射到 `_mbsrev`|
|无 (默认既没有 `_UNICODE` 也没有 `_MBCS` 定义) |SBCS (ASCII)|`_tcsrev` 映射到 `strrev`|

例如，在 tchar 中定义的一般文本函数将 `_tcsrev` 映射到（ `_mbsrev` 如果你 `_MBCS` 在你的程序中定义），如果 `_wcsrev` 已定义，则映射到 `_UNICODE` 。 否则，`_tcsrev` 将映射到 `strrev`。 为了方便编程，tchar 中提供了其他数据类型映射，但 `_TCHAR` 这是最有用的。

### <a name="generic-text-data-type-mappings"></a>一般文本数据类型映射

|Generic-Text<br /> 数据类型名称|_UNICODE &<br /> _MBCS 未定义|_MBCS<br /> 已定义|_UNICODE<br /> 已定义|
|--------------------------------------|----------------------------------------|------------------------|---------------------------|
|`_TCHAR`|**`char`**|**`char`**|**`wchar_t`**|
|`_TINT`|**`int`**|**`unsigned int`**|`wint_t`|
|`_TSCHAR`|**`signed char`**|**`signed char`**|**`wchar_t`**|
|`_TUCHAR`|**`unsigned char`**|**`unsigned char`**|**`wchar_t`**|
|`_TXCHAR`|**`char`**|**`unsigned char`**|**`wchar_t`**|
|`_T` 或 `_TEXT`|无效果（由预处理器删除）|无效果（由预处理器删除）|`L` (将以下字符或字符串转换为其 Unicode 副本) |

有关例程、变量和其他对象的一般文本映射列表，请参阅 Run-Time 库参考中的 [一般文本映射](../c-runtime-library/generic-text-mappings.md) 。

> [!NOTE]
> 不要使用包含 `str` Unicode 字符串的函数系列，它们可能包含嵌入的 null 字节。 同样，不要将 `wcs` 函数系列与 MBCS (或 SBCS) 字符串一起使用。

以下代码片段说明了用于映射到 MBCS、Unicode 和 SBCS 模型的 `_TCHAR` 和 `_tcsrev` 的使用方法。

```cpp
_TCHAR *RetVal, *szString;
RetVal = _tcsrev(szString);
```

如果已 `_MBCS` 定义，则预处理器会将此片段映射到以下代码：

```cpp
char *RetVal, *szString;
RetVal = _mbsrev(szString);
```

如果已 `_UNICODE` 定义，则预处理器会将此片段映射到以下代码：

```cpp
wchar_t *RetVal, *szString;
RetVal = _wcsrev(szString);
```

如果和均未 `_MBCS` `_UNICODE` 定义，则预处理器会将片段映射为单字节 ASCII 代码，如下所示：

```cpp
char *RetVal, *szString;
RetVal = strrev(szString);
```

因此，您可以编写、维护和编译单个源代码文件，以使用特定于三种字符集中的任何一种的例程来运行。

## <a name="see-also"></a>请参阅

[文本和字符串](../text/text-and-strings-in-visual-cpp.md)<br/>
[使用 TCHAR。具有 _MBCS 代码的 H 数据类型](../text/using-tchar-h-data-types-with-mbcs-code.md)
