---
title: Unicode 编程摘要
ms.date: 11/04/2016
helpviewer_keywords:
- Unicode [C++], programming with
- Unicode [C++], MFC and C run-time functions
ms.assetid: a4c9770f-6c9c-447c-996b-980920288bed
ms.openlocfilehash: 5095e1c58db3e5c35eb9215367f2fbb064bc228a
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504717"
---
# <a name="unicode-programming-summary"></a>Unicode 编程摘要

若要利用对 Unicode 的 MFC 和 C 运行时支持，需执行以下操作：

- 定义 `_UNICODE` 。

   在 `_UNICODE` 生成程序之前定义符号。

- 指定入口点。

   在项目的 "[属性页](../build/reference/property-pages-visual-cpp.md)" 对话框中的 "**链接器**" 文件夹的 "**高级**" 页上，将**入口点**符号设置为 `wWinMainCRTStartup` 。

- 使用可移植的运行时函数和类型。

   使用正确的 C 运行时函数进行 Unicode 字符串处理。 你可以使用 `wcs` 函数系列，但你可能更倾向于) 宏的完全可移植 (国际启用 `_TCHAR` 。 这些宏的所有前缀均 `_tcs` 为，它们替换为一 `str` 系列函数。 《*运行时库参考*》中的[国际化](../c-runtime-library/internationalization.md)部分详细介绍了这些函数。 有关详细信息，请参阅 [tchar 中的一般文本映射](../text/generic-text-mappings-in-tchar-h.md)。

   使用 `_TCHAR` 和 [支持 Unicode](../text/support-for-unicode.md)中所述的相关可移植数据类型。

- 正确处理文本字符串。

   Visual C++ 编译器将编码为的文字字符串解释为：

    ```cpp
    L"this is a literal string"
    ```

   表示 Unicode 字符的字符串。 你可以对文本字符使用相同的前缀。 使用 `_T` 宏来一般地编码文本字符串，以便它们在 unicode 或 ANSI 字符串下作为 unicode 字符串编译 (包括 MBCS) （不带 Unicode）。 例如，不是：

    ```cpp
    pWnd->SetWindowText( "Hello" );
    ```

   用法

    ```cpp
    pWnd->SetWindowText( _T("Hello") );
    ```

   如果 `_UNICODE` 定义了，则 `_T` 会将文本字符串转换为 l 前缀的窗体; 否则，将 `_T` 转换不带 l 前缀的字符串。

    > [!TIP]
    >  `_T`宏与宏完全相同 `_TEXT` 。

- 请小心地将字符串长度传递到函数。

   某些函数需要字符串中的字符数;其他人需要字节数。 例如，如果 `_UNICODE` 定义了，则在) 中，对对象的以下调用 `CArchive` 将不起作用 (`str` `CString` ：

    ```cpp
    archive.Write( str, str.GetLength( ) );    // invalid
    ```

   在 Unicode 应用程序中，长度可提供字符数但不是正确的字节数，因为每个字符宽为2个字节。 相反，你必须使用：

    ```cpp
    archive.Write( str, str.GetLength( ) * sizeof( _TCHAR ) );    // valid
    ```

   指定要写入的正确字节数。

   但是，对于面向字符的 MFC 成员函数（而不是面向字节的），无需此额外编码即可工作：

    ```cpp
    pDC->TextOut( str, str.GetLength( ) );
    ```

   `CDC::TextOut` 采用多个字符，而不是字节数。

- 使用 [fopen_s，_wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) 打开 Unicode 文件。

总而言之，MFC 和运行时库为 Unicode 编程提供了以下支持：

- 除了数据库类成员函数，所有 MFC 函数都启用了 Unicode，其中包括 `CString` 。 `CString` 还提供了 Unicode/ANSI 转换函数。

- 运行时库提供所有字符串处理函数的 Unicode 版本。  (运行库还提供适用于 Unicode 或 MBCS 的可移植版本。 这些是 `_tcs` 宏。 ) 

- tchar 提供可移植的数据类型和 `_T` 用于转换文本字符串和字符的宏。 有关详细信息，请参阅 [tchar 中的一般文本映射](../text/generic-text-mappings-in-tchar-h.md)。

- 运行时库提供了的宽字符版本 `main` 。 用于 `wmain` 使应用程序能够识别 Unicode。

## <a name="see-also"></a>请参阅

[支持 Unicode](../text/support-for-unicode.md)
