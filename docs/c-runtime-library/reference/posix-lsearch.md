---
description: 了解详细信息： lsearch
title: lsearch
ms.date: 12/16/2019
api_name:
- lsearch
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
- lsearch
helpviewer_keywords:
- lsearch function
ms.assetid: 130da3fc-904a-4375-b0ab-79bfea8a455f
ms.openlocfilehash: 6036c21c37a6b96a0adb906f7905d24e39769da3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296233"
---
# <a name="lsearch"></a>lsearch

Microsoft 实现的 POSIX 函数名称 `lsearch` 是 [_lsearch](lsearch.md) 函数的不推荐使用的别名。 默认情况下，它会生成 [编译器警告 (等级 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)。 名称已弃用，因为它不遵循特定于实现的名称的标准 C 规则。 但是，该函数仍受支持。

建议改用 [_lsearch](lsearch.md) 或安全增强 [_lsearch_s](lsearch-s.md) 函数。 或者，你可以继续使用此函数名称，并禁用警告。 有关详细信息，请参阅 [关闭警告](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) 和 [POSIX 函数名称](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)。
