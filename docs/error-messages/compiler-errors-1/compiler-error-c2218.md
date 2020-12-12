---
description: 了解更多：编译器错误 C2218
title: 编译器错误 C2218
ms.date: 11/04/2016
f1_keywords:
- C2218
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
ms.openlocfilehash: d2761bb822c5a1055974e4a0bcd6011e7f451821
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245520"
---
# <a name="compiler-error-c2218"></a>编译器错误 C2218

> “__vectorcall”不能和“/arch:IA32”一起使用

**`__vectorcall`** 只支持在 x86 和 x64 处理器上的本机代码中提供调用约定，其中包括流式处理 Simd 扩展 2 (SSE2) 和更高版本。 有关详细信息，请参阅 [`__vectorcall`](../../cpp/vectorcall.md)。

若要修复此错误，请将编译器选项更改为目标 SSE2、AVX 或 AVX2 指令集的。 有关详细信息，请参阅 `/arch` (x86)。
