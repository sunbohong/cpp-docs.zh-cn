---
description: 详细了解：指针减法
title: 指针减法
ms.date: 11/04/2016
helpviewer_keywords:
- pointer subtraction
ms.assetid: 4d515690-088a-43f6-bb8c-57b849f7ccf7
ms.openlocfilehash: a2f5c252ad61cd990d6f890431a8d3107f303a75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195887"
---
# <a name="pointer-subtraction"></a>指针减法

**ANSI 3.3.6, 4.1.1** 保留两个指向同一数组 ptrdiff_t  的元素的指针之间的差所需的整数类型

在 32 位 x86 平台上，`ptrdiff_t` typedef 是 `int`。 在 64 位平台上，`ptrdiff_t` typedef 是 `__int64`。

## <a name="see-also"></a>请参阅

[数组和指针](../c-language/arrays-and-pointers.md)
