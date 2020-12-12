---
description: 了解详细信息：链接器工具警告 LNK4237
title: 链接器工具警告 LNK4237
ms.date: 11/04/2016
f1_keywords:
- LNK4237
helpviewer_keywords:
- LNK4237
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
ms.openlocfilehash: 9f8af2d6f0fa2d1153af749e327e95b863ed6914
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259989"
---
# <a name="linker-tools-warning-lnk4237"></a>链接器工具警告 LNK4237

/SUBSYSTEM：从 "dll" 导入时指定了 NATIVE;使用/SUBSYSTEM： CONSOLE 或/SUBSYSTEM： WINDOWS。

[/SUBSYSTEM：](../../build/reference/subsystem-specify-subsystem.md) 生成一个直接使用以下一项或多项的 Windows (Win32) 应用程序时指定了 NATIVE：

- Kernel32.dll

- gdi32.dll

- user32.dll

- msvcrt.lib \* dll 之一。

不指定 **/SUBSYSTEM： NATIVE** 来解决此警告。
