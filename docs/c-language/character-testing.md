---
description: 详细了解：字符测试
title: 字符测试
ms.date: 11/04/2016
ms.assetid: 376ba061-bae3-427e-9569-33fa5949a199
ms.openlocfilehash: b7d73bce671787622814e11d8f3add7a1092572a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190531"
---
# <a name="character-testing"></a>字符测试

**ANSI 4.3.1**：由 `isalnum`、`isalpha`、`iscntrl`、`islower`、`isprint` 和 `isupper` 函数测试的字符集

以下列表描述了由 Microsoft C 编译器实现的这些函数。

|函数|测试|
|--------------|---------------|
|`isalnum`|字符 0 - 9、A-Z、a–z ASCII 48-57、65-90、97-122|
|`isalpha`|字符 A-Z、a–z ASCII 65-90、97-122|
|`iscntrl`|ASCII 0 -31、127|
|`islower`|字符 a-z ASCII 97-122|
|`isprint`|字符 A–Z、a–z、0 - 9、标点、空格 ASCII 32–126|
|`isupper`|字符 A-Z ASCII 65-90|

## <a name="see-also"></a>请参阅

[库函数](../c-language/library-functions.md)
