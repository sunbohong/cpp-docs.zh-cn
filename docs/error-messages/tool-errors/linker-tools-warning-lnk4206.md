---
description: 了解详细信息：链接器工具警告 LNK4206
title: 链接器工具警告 LNK4206
ms.date: 12/05/2017
f1_keywords:
- LNK4206
helpviewer_keywords:
- LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
ms.openlocfilehash: 40d7a8f18a835721ff747293696d0499c0a94ef3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294140"
---
# <a name="linker-tools-warning-lnk4206"></a>链接器工具警告 LNK4206

> 未找到预编译类型信息;未链接或覆盖 "*filename*";正在链接对象，如同没有调试信息一样

使用 [/yc](../../build/reference/yc-create-precompiled-header-file.md)编译的 *filename* 对象文件未在 LINK 命令中指定或已被覆盖。

当使用/Yc 编译的 .obj 位于库中，并且代码中没有对该 .obj 的符号引用时，会出现此警告的常见情况。  在这种情况下，链接器将不使用 (甚至) .obj 文件。  在这种情况下，应重新编译代码，并将 [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) 用于使用 [/yu](../../build/reference/yu-use-precompiled-header-file.md)编译的对象。
