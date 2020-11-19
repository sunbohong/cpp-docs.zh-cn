---
title: 内存分配
ms.date: 11/18/2020
description: 用于分配、释放和重新分配内存的 Microsoft C 运行时函数的列表。
f1_keywords:
- c.memory
helpviewer_keywords:
- memory allocation, routines
- memory, managing
- memory, allocation
ms.openlocfilehash: 39be48a4ebdf8ee917395d7b743846196200878d
ms.sourcegitcommit: e82e13b80150fcb27a1387018aafb00d99a3827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "94920737"
---
# <a name="memory-allocation"></a>内存分配

这些例程分配、释放和重新分配内存。

## <a name="memory-allocation-routines"></a>内存分配例程

|例程所返回的值|用途|
|-------------|---------|
|[`_alloca`](../c-runtime-library/reference/alloca.md), [`_malloca`](../c-runtime-library/reference/malloca.md)|从堆栈中分配内存|
|[`calloc`](../c-runtime-library/reference/calloc.md)|分配一个数组，并将其元素初始化为 0 (零) |
|[`_calloc_dbg`](../c-runtime-library/reference/calloc-dbg.md)|的调试版本 **`calloc`** 。 仅在运行时库的调试版本中可用|
|[`operator delete`, `operator delete[]`](../c-runtime-library/delete-operator-crt.md)|在堆上分配的可用内存 |
|[`_expand`](../c-runtime-library/reference/expand.md)|展开或收缩内存块，而无需移动它|
|[`_expand_dbg`](../c-runtime-library/reference/expand-dbg.md)|的调试版本 **`_expand`** 。 仅在运行时库的调试版本中可用|
|[`free`](../c-runtime-library/reference/free.md)|在堆上分配的可用内存|
|[`_free_dbg`](../c-runtime-library/reference/free-dbg.md)|的调试版本 **`free`** 。 仅在运行时库的调试版本中可用|
|[`_freea`](../c-runtime-library/reference/freea.md)|在堆栈上分配的可用内存|
|[`_get_heap_handle`](../c-runtime-library/reference/get-heap-handle.md)|`HANDLE` (CRT) 堆获取 Win32 到 C 运行时。|
|[`_heapadd`](../c-runtime-library/heapadd.md)|将内存添加到堆|
|[`_heapchk`](../c-runtime-library/reference/heapchk.md)|检查堆的一致性|
|[`_heapmin`](../c-runtime-library/reference/heapmin.md)|释放堆中未使用的内存|
|[`_heapset`](../c-runtime-library/heapset.md)|用值填充免费堆条目|
|[`_heapwalk`](../c-runtime-library/reference/heapwalk.md)|获取有关堆中每个条目的信息|
|[`malloc`](../c-runtime-library/reference/malloc.md)|从堆中分配内存|
|[`_malloc_dbg`](../c-runtime-library/reference/malloc-dbg.md)|的调试版本 **`malloc`** ; 仅在运行时库的调试版本中可用|
|[`_msize`](../c-runtime-library/reference/msize.md)|返回分配的内存块的大小|
|[`_msize_dbg`](../c-runtime-library/reference/msize-dbg.md)|的调试版本 **`_msize`** ; 仅在运行时库的调试版本中可用|
|[`new`, `new[]`](../c-runtime-library/new-operator-crt.md)|从堆中分配内存块|
|[`_query_new_handler`](../c-runtime-library/reference/query-new-handler.md)|获取由设置的当前新处理程序例程的地址 **`_set_new_handler`**|
|[`_query_new_mode`](../c-runtime-library/reference/query-new-mode.md)|获取为设置的新处理程序模式 **`_set_new_mode`****`malloc`**|
|[`realloc`](../c-runtime-library/reference/realloc.md)|将块重新分配到新大小|
|[`_realloc_dbg`](../c-runtime-library/reference/realloc-dbg.md)|的调试版本 **`realloc`** ; 仅在运行时库的调试版本中可用|
|[`_set_new_handler`](../c-runtime-library/reference/set-new-handler.md)|如果 **`new`** 运算符无法分配内存，则启用错误处理机制，并启用 c + + 标准库的编译|
|[`_set_new_mode`](../c-runtime-library/reference/set-new-mode.md)|设置的新处理程序模式 **`malloc`**|

## <a name="see-also"></a>请参阅

[按类别分的通用 C 运行时例程](../c-runtime-library/run-time-routines-by-category.md)