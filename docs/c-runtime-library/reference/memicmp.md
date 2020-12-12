---
description: 了解详细信息： memicmp
title: memicmp
ms.date: 12/16/2019
api_name:
- memicmp
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- memicmp
helpviewer_keywords:
- memicmp function
ms.assetid: 45362e9c-7c64-41e9-92bb-7d4999a8635b
ms.openlocfilehash: 7e3596a6a2d2317c72645b4fbd8a2d0faae9d147
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97171421"
---
# <a name="memicmp"></a>memicmp

特定于 Microsoft 的函数名称 `memicmp` 是 [_memicmp](memicmp-memicmp-l.md) 函数的不推荐使用的别名。 默认情况下，它会生成 [编译器警告 (等级 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)。 名称已弃用，因为它不遵循特定于实现的名称的标准 C 规则。 但是，该函数仍受支持。

建议改用 [_memicmp](memicmp-memicmp-l.md) 。 或者，你可以继续使用此函数名称，并禁用警告。 有关详细信息，请参阅 [关闭警告](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) 和 [POSIX 函数名称](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)。
