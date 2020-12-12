---
description: 了解更多：打开
title: 开门
ms.date: 12/16/2019
api_name:
- open
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
- open
helpviewer_keywords:
- open function
ms.assetid: e3139118-4da2-434b-a551-fcf3fccf49b5
ms.openlocfilehash: 65dc30f24737e1071deedead78d0b8267e4de97b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195640"
---
# <a name="open"></a>开门

Microsoft 实现的 POSIX 函数名称 `open` 是 [_open](open-wopen.md) 函数的不推荐使用的别名。 默认情况下，它会生成 [编译器警告 (等级 3) C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)。 名称已弃用，因为它不遵循特定于实现的名称的标准 C 规则。 但是，该函数仍受支持。

建议改用 [_open](open-wopen.md) 。 或者，你可以继续使用此函数名称，并禁用警告。 有关详细信息，请参阅 [关闭警告](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#turn-off-the-warning) 和 [POSIX 函数名称](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)。
