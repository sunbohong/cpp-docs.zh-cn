---
description: '了解详细信息：支持多字节字符集 (Mbcs) '
title: 支持多字节字符集 (MBCS)
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- multibyte characters [C++]
- MBCS [C++]
ms.assetid: b498733c-a1e1-45e3-8f26-d6da3cb5f2dd
ms.openlocfilehash: 8ab6af7aa77942b39785faf68ea6a530867abff8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335766"
---
# <a name="support-for-multibyte-character-sets-mbcss"></a>支持多字节字符集 (MBCS)

多字节字符集 (MBCS) 是一种支持无法用单字节表示的字符集（如日语和中文）的旧方法。 如果要进行新的开发，则应对所有文本字符串（最终用户不会看到的系统字符串也许可以除外）使用 Unicode。 MBCS 是旧技术，不建议用于新开发。

最常见的 MBCS 实现是双字节字符集 (DBCS)。 通常，Visual C++（尤其是 MFC）对 DBCS 完全启用。

有关示例，请参阅 MFC 源代码文件。

对于在其语言使用大型字符集的市场中使用的平台，Unicode 的最佳备选方法是 MBCS。 MFC 通过使用可国际化的数据类型和 C 运行时函数来支持 MBCS。 应在你的代码中执行相同操作。

在 MBCS 下，字符以 1 或 2 字节进行编码。 在 2 字节字符中，第一个字节或前导字节会发出信号，表示它和下一个字节将被解释为一个字符。 第一个字节来自保留用作前导字节的代码范围。 哪个范围的字节可以是前导字节取决于正在使用的代码页。 例如，日语代码页 932 将 0x81 到 0x9F 的范围用作前导字节，而朝鲜语代码页 949 使用不同的范围。

请在 MBCS 编程中考虑以下各方面。

环境中的 MBCS 字符可以出现在字符串中，如文件和目录名称。

### <a name="editing-operations"></a>编辑操作

MBCS 应用程序中的编辑操作应在字符上（而不是在字节上）执行。 脱字号不应拆分字符， **向右箭头** 键应向右移动一个字符，依此类推。 **Delete** 应删除一个字符; **Undo** 应重新插入它。

### <a name="string-handling"></a>字符串处理

在使用 MBCS 的应用程序中，字符串处理会引起特殊问题。 在单一字符串中混合使用两种宽度的字符；因此，你必须记得检查前导字节。

### <a name="run-time-library-support"></a>运行时库支持

C 运行时库和 MFC 支持单字节、MBCS 和 Unicode 编程。 单字节字符串通过 `str` 运行时函数系列处理，用相应的函数处理 MBCS 字符串 `_mbs` ，并通过相应的函数处理 Unicode 字符串 `wcs` 。 MFC 类成员函数的实现使用可移植运行时函数，该函数在适当情况下映射到 `str` 系列的函数、MBCS 函数或 Unicode 函数，如“MBCS/Unicode 可移植性”中所述。

### <a name="mbcsunicode-portability"></a>MBCS/Unicode 可移植性

使用 tchar 头文件，可以从相同的源构建单字节、MBCS 和 Unicode 应用程序。 Tchar 定义了带 *_tcs* 前缀的宏，该宏将 `str` 根据需要映射到、 `_mbs` 或 `wcs` 函数。 若要生成 MBCS，请定义符号 `_MBCS` 。 若要生成 Unicode，请定义符号 `_UNICODE` 。 默认情况下， `_UNICODE` 为 MFC 应用程序定义。 有关详细信息，请参阅 [tchar 中的一般文本映射](../text/generic-text-mappings-in-tchar-h.md)。

> [!NOTE]
> 如果同时定义和，则行为是不确定的 `_UNICODE` `_MBCS` 。

Mbctype.h 和 Mbstring.h 头文件定义特定于 MBCS 的函数和宏，你可能在某些情况下需要它们。 例如，`_ismbblead` 告诉你字符串中的特定字节是否为前导字节。

为实现国际便携性，请用 [Unicode](../text/support-for-unicode.md) 或多字节字符集来编写程序代码， (mbcs) 。

## <a name="what-do-you-want-to-do"></a>你希望做什么？

- [在我的程序中启用 MBCS](../text/international-enabling.md)

- [在我的程序中启用 Unicode 和 MBCS](../text/internationalization-strategies.md)

- [使用 MBCS 创建国际化程序](../text/mbcs-programming-tips.md)

- [请参阅 Unicode 编程摘要](../text/mbcs-programming-tips.md)

- [了解字节宽度可移植性的一般文本映射](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>请参阅

[文本和字符串](../text/text-and-strings-in-visual-cpp.md)<br/>
[Visual C++ 中的 MBCS 支持](../text/mbcs-support-in-visual-cpp.md)
