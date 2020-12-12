---
description: '了解详细信息： access (CRT) '
title: access (CRT)
ms.date: 12/16/2019
api_name:
- access
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
- access
helpviewer_keywords:
- access function
ms.assetid: 65197793-bd0a-41c3-9c29-18de2d95d9a6
ms.openlocfilehash: 2ebfffcdc73f77a083ed5a1f29b34e2cd2e0b76a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97303868"
---
# <a name="access-crt"></a>access (CRT)

Microsoft 实现的 POSIX 函数名称 `access` 是 [_access](access-waccess.md) 函数的不推荐使用的别名。 默认情况下，它会生成 [编译器警告 (等级 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)。 名称已弃用，因为它不遵循特定于实现的名称的标准 C 规则。 但是，该函数仍受支持。

建议改用 [_access](access-waccess.md) 或安全增强 [_access_s](access-s-waccess-s.md) 函数。 或者，你可以继续使用此函数名称，并禁用警告。 有关详细信息，请参阅 [关闭警告](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) 和 [POSIX 函数名称](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)。
