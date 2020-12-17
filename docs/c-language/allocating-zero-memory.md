---
description: 详细了解：分配零内存
title: 分配零内存
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
ms.openlocfilehash: 7971d9e097d00607af2acf4590ff3daaf67f7127
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280139"
---
# <a name="allocating-zero-memory"></a>分配零内存

**ANSI 4.10.3** 请求的大小为零时，`calloc`、`malloc` 或 `realloc` 函数的行为

`calloc`、`malloc` 和 `realloc` 函数接受零作为参数。 不分配实际内存，但会返回有效的指针，并且之后可通过 realloc 修改内存块。

## <a name="see-also"></a>请参阅

[库函数](../c-language/library-functions.md)
