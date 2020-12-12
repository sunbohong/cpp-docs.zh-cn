---
description: 了解详细信息：链接器工具警告 LNK4086
title: 链接器工具警告 LNK4086
ms.date: 11/04/2016
f1_keywords:
- LNK4086
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
ms.openlocfilehash: f19138d895706579cff13bd1d43b9a64ccaa5044
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210109"
---
# <a name="linker-tools-warning-lnk4086"></a>链接器工具警告 LNK4086

入口点 "function" 与参数的 "number" 个字节不 __stdcall;映像可能无法运行

DLL 的入口点必须是 **`__stdcall`** 。 在定义函数时，可以用 [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) 选项重新编译该函数，也可以指定 **`__stdcall`** 或 WINAPI。
