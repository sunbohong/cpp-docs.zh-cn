---
description: 详细了解：system 函数
title: 系统函数
ms.date: 11/04/2016
helpviewer_keywords:
- system function
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
ms.openlocfilehash: 094fb3be58c1ff82c823ff79c4181a46b7ddf14c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114375"
---
# <a name="system-function"></a>系统函数

**ANSI 4.10.4.5**  system 函数执行字符串的内容和模式

 system 函数执行内部操作系统命令，或者 C 程序中（而不是命令行中）的 .EXE、.COM（Windows NT 中的 .CMD）或 .BAT 文件。

系统函数查找命令解释器，它通常是 Windows NT 操作系统中的 CMD.EXE 或 Windows 中的 COMMAND.COM。 系统函数随后将自变量字符串传递到命令解释器。

有关详细信息，请参阅 [system、_wsystem](../c-runtime-library/reference/system-wsystem.md)。

## <a name="see-also"></a>请参阅

[库函数](../c-language/library-functions.md)
