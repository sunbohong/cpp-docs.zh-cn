---
description: 了解详细信息： strnicmp、wcsnicmp
title: strnicmp、wcsnicmp
ms.date: 12/16/2019
api_name:
- wcsnicmp
- strnicmp
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
- wcsnicmp
- strnicmp
helpviewer_keywords:
- strnicmp function
- wcsnicmp function
ms.assetid: 01324ee4-0bd9-43e9-b2a3-53d180270a64
ms.openlocfilehash: f69874c6dedb72ad0ef2b44f468e2d08236302d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306048"
---
# <a name="strnicmp-wcsnicmp"></a>strnicmp、wcsnicmp

特定于 Microsoft 的函数名称 `strnicmp` 和 `wcsnicmp` 是 [_strnicmp 和 _wcsnicmp](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md) 函数的不推荐使用的别名。 默认情况下，它们 [ (级别 3) C4996 生成编译器警告](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)。 名称已弃用，因为它们不遵循特定于实现的名称的标准 C 规则。 但仍支持这些函数。

建议改用 [_strnicmp 和 _wcsnicmp](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md) 。 或者，你可以继续使用这些函数名，并禁用警告。 有关详细信息，请参阅 [关闭警告](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) 和 [POSIX 函数名称](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)。
