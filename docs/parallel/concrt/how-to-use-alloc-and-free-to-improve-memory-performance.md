---
description: 了解有关的详细信息：如何：使用分配和自由提高内存性能
title: 如何：使用 Alloc 和 Free 提高内存性能
ms.date: 11/04/2016
helpviewer_keywords:
- Alloc and Free, using [Concurrency Runtime]
- Using Alloc and Free [Concurrency Runtime]
ms.assetid: e1fab9e8-a97d-4104-bead-e95958db79f9
ms.openlocfilehash: ab9a7bb9ad067bd7a5650b9e66d1708f08ffc183
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172565"
---
# <a name="how-to-use-alloc-and-free-to-improve-memory-performance"></a>如何：使用 Alloc 和 Free 提高内存性能

本文档演示如何使用 [concurrency：：分配](reference/concurrency-namespace-functions.md#alloc) 和 [Concurrency：： Free](reference/concurrency-namespace-functions.md#free) 函数提高内存性能。 它将为两个不同类型（每个指定和运算符）并行反转数组的元素所需的时间进行 `new` 比较 `delete` 。

`Alloc` `Free` 当多个线程频繁调用和时，和函数最 `Alloc` 有用 `Free` 。 运行时为每个线程保留单独的内存缓存;因此，运行时在不使用锁或内存屏障的情况下管理内存。

## <a name="example-types-that-specify-new-and-delete-operators"></a>示例：指定 new 和 delete 运算符的类型

下面的示例演示三种类型，分别指定 `new` 和 `delete` 运算符。 `new_delete`类使用 global `new` 和 `delete` 运算符， `malloc_free` 类使用 C 运行时[malloc](../../c-runtime-library/reference/malloc.md)和[free](../../c-runtime-library/reference/free.md)函数， `Alloc_Free` 类使用并发运行时 `Alloc` 和 `Free` 函数。

[!code-cpp[concrt-allocators#1](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_1.cpp)]

## <a name="example-swap-and-reverse_array-functions"></a>示例： swap 和 reverse_array 函数

下面的示例显示 `swap` 和 `reverse_array` 函数。 `swap`函数交换指定索引处的数组内容。 它为临时变量从堆中分配内存。 `reverse_array`函数创建一个大型数组，并计算一次将此数组并行反转所需的时间。

[!code-cpp[concrt-allocators#2](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_2.cpp)]

## <a name="example-wmain-function"></a>示例： wmain 函数

下面的示例演示 `wmain` 函数，该函数计算函数对、和类型执行操作所需的时间 `reverse_array` `new_delete` `malloc_free` `Alloc_Free` ，每个操作都使用不同的内存分配方案。

[!code-cpp[concrt-allocators#3](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_3.cpp)]

## <a name="complete-code-example"></a>完整代码示例

下面是完整的示例。

[!code-cpp[concrt-allocators#4](../../parallel/concrt/codesnippet/cpp/how-to-use-alloc-and-free-to-improve-memory-performance_4.cpp)]

此示例为具有四个处理器的计算机生成以下示例输出。

```Output
Took 2031 ms with new/delete.
Took 1672 ms with malloc/free.
Took 656 ms with Alloc/Free.
```

在此示例中，使用 `Alloc` 和函数的类型 `Free` 提供最佳的内存性能，因为 `Alloc` 和 `Free` 函数经过优化，可用于从多个线程频繁地分配和释放内存块。

## <a name="compiling-the-code"></a>编译代码

复制代码示例并将其粘贴到 Visual Studio 项目中，或粘贴到一个名为的文件中， `allocators.cpp` 然后在 Visual Studio 命令提示符窗口中运行以下命令。

> **cl.exe/EHsc 分配器**

## <a name="see-also"></a>请参阅

[内存管理函数](../../parallel/concrt/memory-management-functions.md)<br/>
[Alloc 函数](reference/concurrency-namespace-functions.md#alloc)<br/>
[Free 函数](reference/concurrency-namespace-functions.md#free)
