---
description: 了解详细信息： strrev、wcsrev
title: strrev、wcsrev
ms.date: 12/16/2019
api_name:
- strrev
- wcsrev
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
- strrev
- wcsrev
helpviewer_keywords:
- strrev function
- wcsrev function
ms.assetid: 89e05854-a9ce-4fb7-993d-a9831cd7edf2
ms.openlocfilehash: 2f9cb8e5a1a0bce09b0da030392d6b459f16c967
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209420"
---
# <a name="strrev-wcsrev"></a>strrev、wcsrev

特定于 Microsoft 的函数名称 `strrev` 和 `wcsrev` 是 [_strrev 和 _wcsrev](strrev-wcsrev-mbsrev-mbsrev-l.md) 函数的不推荐使用的别名。 默认情况下，它们 [ (级别 3) C4996 生成编译器警告](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)。 名称已弃用，因为它们不遵循特定于实现的名称的标准 C 规则。 但仍支持这些函数。

建议改用 [_strrev 和 _wcsrev](strrev-wcsrev-mbsrev-mbsrev-l.md) 。 或者，你可以继续使用这些函数名，并禁用警告。 有关详细信息，请参阅 [关闭警告](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) 和 [POSIX 函数名称](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)。
