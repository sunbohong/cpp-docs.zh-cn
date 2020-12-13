---
description: 了解详细信息：国际化策略
title: 国际化策略
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- language-portable code [C++]
- MBCS [C++], internationalization strategies
- Windows API [C++], international programming strategies
- Win32 [C++], international programming strategies
- Unicode [C++], globalizing applications
- character sets [C++], international programming strategies
- localization [C++], character sets
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
ms.openlocfilehash: 51570a3e340a8af0a9f16f8212aa11f6bf3119b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331179"
---
# <a name="internationalization-strategies"></a>国际化策略

根据你的目标操作系统和市场，你有多个国际化策略：

- 应用程序使用 Unicode。

   使用 Unicode 特定的功能，所有字符都是16位范围 (虽然您可以在程序的某些部分中使用 ANSI 字符，以进行特殊的) 。 C 运行时库为仅 Unicode 编程提供函数、宏和数据类型。 MFC 完全启用了 Unicode。

- 你的应用程序使用 MBCS，并且可以在任何 Win32 平台上运行。

   使用 MBCS 特定的功能。 字符串可以包含单字节字符和/或双字节字符。 C 运行时库为仅 MBCS 编程提供函数、宏和数据类型。 MFC 完全启用 MBCS。

- 你的应用程序的源代码是通过使用符号或定义的符号重新编译来编写的 `_UNICODE` `_MBCS` ，因此你可以生成使用上述任一方法的版本。 有关详细信息，请参阅 [tchar 中的一般文本映射](../text/generic-text-mappings-in-tchar-h.md)。

   使用完全可移植的 C 运行时函数、宏和数据类型。 MFC 的灵活性支持其中的任何一种策略。

这些主题的其余部分重点介绍如何编写可作为 Unicode 或 MBCS 构建的完全可移植代码。

## <a name="see-also"></a>请参阅

[Unicode 和 MBCS](../text/unicode-and-mbcs.md)<br/>
[区域设置和代码页](../text/locales-and-code-pages.md)
