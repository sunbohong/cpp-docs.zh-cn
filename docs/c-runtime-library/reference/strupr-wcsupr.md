---
description: 了解详细信息： strupr、wcsupr
title: strupr、wcsupr
ms.date: 12/16/2019
api_name:
- strupr
- wcsupr
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
- strupr
- wcsupr
helpviewer_keywords:
- strupr function
- wcsupr function
ms.assetid: 17dfe1cd-3b09-4702-9f89-2207f44953e6
ms.openlocfilehash: aefd25cc4d2a8d3fa51fba2da323c74ed199d116
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326276"
---
# <a name="strupr-wcsupr"></a>strupr、wcsupr

特定于 Microsoft 的函数名称 `strupr` 和 `wcsupr` 是 [_strupr 和 _wcsupr](strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md) 函数的不推荐使用的别名。 默认情况下，它们 [ (级别 3) C4996 生成编译器警告](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)。 名称已弃用，因为它们不遵循特定于实现的名称的标准 C 规则。 但仍支持这些函数。

建议改用 [_strupr 和 _wcsupr](strupr-strupr-l-mbsupr-mbsupr-l-wcsupr-l-wcsupr.md) 或安全增强型 [_strupr_s 和 _wcsupr_s](strupr-s-strupr-s-l-mbsupr-s-mbsupr-s-l-wcsupr-s-wcsupr-s-l.md) 函数。 或者，你可以继续使用这些函数名，并禁用警告。 有关详细信息，请参阅 [关闭警告](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) 和 [POSIX 函数名称](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)。
