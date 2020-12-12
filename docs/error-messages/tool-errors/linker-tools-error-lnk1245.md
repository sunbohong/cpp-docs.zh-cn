---
description: 了解详细信息：链接器工具错误 LNK1245
title: 链接器工具错误 LNK1245
ms.date: 11/04/2016
f1_keywords:
- LNK1245
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
ms.openlocfilehash: 3903651992f8fb79c3a79e4f2afc9d84e70e8126
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193898"
---
# <a name="linker-tools-error-lnk1245"></a>链接器工具错误 LNK1245

指定的子系统 "子系统" 无效;/SUBSYSTEM 必须是 WINDOWS、WINDOWSCE 或 CONSOLE

使用[/clr](../../build/reference/clr-common-language-runtime-compilation.md)编译对象，并满足以下条件之一：

- 自定义入口点是 ([/ENTRY](../../build/reference/entry-entry-point-symbol.md)) 定义的，使链接器无法推断子系统。

- 向 [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) 链接器选项传递的值对于/clr 对象无效。

对于这两种情况，解决方法是为/SUBSYSTEM 链接器选项指定有效值。
