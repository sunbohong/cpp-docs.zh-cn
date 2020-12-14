---
description: 了解详细信息：内存管理：可调整大小的内存块
title: 内存管理：可调整大小的内存块
ms.date: 11/04/2016
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
ms.openlocfilehash: bcca5617a0d59a7dd5c6a1f9c9f82cb5876f1ef5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248874"
---
# <a name="memory-management-resizable-memory-blocks"></a>内存管理：可调整大小的内存块

**`new`** **`delete`** [内存管理：示例](memory-management-examples.md)一文中介绍了和运算符，适用于分配固定大小的内存块和对象并对其进行分配。 有时，应用程序可能需要可调整大小的内存块。 必须使用标准 C 运行时库函数 [malloc](../c-runtime-library/reference/malloc.md)、 [realloc](../c-runtime-library/reference/realloc.md)和 [free](../c-runtime-library/reference/free.md) ，以管理堆上可调整大小的内存块。

> [!IMPORTANT]
> **`new`** **`delete`** 将和运算符与同一内存块上可调整大小的内存分配函数混合在一起会导致 MFC 调试版本中的内存损坏。 不应在使用分配的内存块上使用 realloc **`new`** 。 同样，你不应使用运算符分配内存块 **`new`** 并将其删除，也不应 **`delete`** 在使用 **malloc** 分配的内存块上使用运算符。

## <a name="see-also"></a>请参阅

[内存管理：堆分配](memory-management-heap-allocation.md)
