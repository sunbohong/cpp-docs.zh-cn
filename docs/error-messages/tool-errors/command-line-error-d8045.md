---
description: 了解详细信息： Command-Line 错误 D8045
title: 命令行错误 D8045
ms.date: 11/04/2016
f1_keywords:
- D8045
helpviewer_keywords:
- D8045
ms.assetid: 01c8808c-bac1-4b4d-8a90-b595f95e9318
ms.openlocfilehash: 0445454a1e44e85b43fa0302867d9109e9ee3e38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115594"
---
# <a name="command-line-error-d8045"></a>命令行错误 D8045

无法用/clr 选项编译 C 文件 "file"

只有 c + + 源代码文件才能传递到使用 **/clr** 的编译。  使用 **/tp** 将 .c 文件编译为 .cpp 文件;有关详细信息，请参阅 [/tc、/tp、/tc、/tp (指定源文件类型)](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) 。

有关详细信息，请参阅 [/clr (公共语言运行时编译) ](../../build/reference/clr-common-language-runtime-compilation.md)。

如果使用 Visual C++ 编译 ATL 应用程序，也可能会发生 D8045。 有关详细信息，请参阅 [如何：迁移到/clr](../../dotnet/how-to-migrate-to-clr.md) 。
