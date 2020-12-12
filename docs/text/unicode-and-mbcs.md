---
description: 了解更多： Unicode 和 MBCS
title: Unicode 和 MBCS
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], Unicode
- MFC [C++], character sets
- character sets [C++], multibyte
- run-time libraries [C++], language portability
- character sets [C++], Unicode
- Unicode [C++], MFC and C run-time functions
- multibyte characters [C++]
- runtime [C++], language portability
ms.assetid: 677baec6-71b4-4579-94df-64f18bc117c4
ms.openlocfilehash: 4fc5afc447612a3f08067185072cd4f116ab80c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114970"
---
# <a name="unicode-and-mbcs"></a>Unicode 和 MBCS

Microsoft 基础类 (MFC) 库、用于 Visual C++ 的 C 运行时库以及启用 Visual C++ 开发环境以帮助你进行国际化编程。 这些映像具有以下特性：

- 支持 Windows 上的 Unicode 标准。 Unicode 是最新的标准，应该尽可能使用它。

   Unicode 是16位字符编码，为所有语言提供足够的编码。 所有 ASCII 字符都作为加宽字符包含在 Unicode 中。

- 支持在所有平台上将多字节字符集 (MBCS) 称为双字节字符集 (DBCS) 。

   DBCS 字符由1或2个字节组成。 某些范围的字节被设置为用作前导字节。 前导字节指定它和以下结尾字节构成单个双字节宽字符。 您必须跟踪哪些字节是前导字节。 在特定的多字节字符集中，前导字节位于某个范围内，尾字节也是如此。 当这些范围重叠时，可能需要对上下文进行评估，以确定给定的字节是用作前导字节还是尾字节。

- 支持简化为国际市场编写的应用程序编程的工具。

   在已启用 MBCS 的 Windows 操作系统版本上运行时，Visual C++ 开发系统（包括集成源代码编辑器、调试器和命令行工具）完全启用了 MBCS。 有关详细信息，请参阅 [Visual C++ 中的 MBCS 支持](../text/mbcs-support-in-visual-cpp.md)。

> [!NOTE]
> 在本文档中，MBCS 用于描述多字节字符的所有非 Unicode 支持。 在 Visual C++ 中，MBCS 始终表示 DBCS。 不支持大于2字节的字符集。

按照定义，ASCII 字符集是所有多字节字符集的子集。 在许多多字节字符集中，0x00 - 0x7F 范围内的每个字符都与 ASCII 字符集中具有相同值的字符相同。 例如，在 ASCII 和 MBCS 字符串中，1字节空字符 ( "\ 0" ) 的值为0x00 并指示终止 NULL 字符。

## <a name="see-also"></a>请参阅

[文本和字符串](../text/text-and-strings-in-visual-cpp.md)<br/>
[国际化启用](../text/international-enabling.md)
