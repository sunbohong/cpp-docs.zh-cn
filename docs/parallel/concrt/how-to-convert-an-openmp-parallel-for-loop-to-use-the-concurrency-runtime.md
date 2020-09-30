---
title: 如何：转换 OpenMP parallel for 循环以使用并发运行时
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, parallel for loops
- converting from OpenMP to the Concurrency Runtime, parallel loops
- parallel for loops, converting from OpenMP to the Concurrency Runtime
- parallel loops, converting from OpenMP to the Concurrency Runtime
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
ms.openlocfilehash: 4f523f9f6de7f1ffb4c3b578b60de587239dffb6
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507883"
---
# <a name="how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime"></a>如何：转换 OpenMP parallel for 循环以使用并发运行时

此示例演示如何转换使用 OpenMP [并行](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) 和 [for](../openmp/reference/openmp-directives.md#for-openmp) 指令的基本循环，以使用并发运行时 [Concurrency：:p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) 算法。

## <a name="example---prime-count"></a>示例-质数计数

此示例使用 OpenMP 和并发运行时来计算随机值数组中质数的计数。

[!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]

本示例生成以下输出。

```Output
Using OpenMP...
found 107254 prime numbers.
Using the Concurrency Runtime...
found 107254 prime numbers.
```

`parallel_for`算法和 OpenMP 3.0 允许索引类型为带符号整型类型或无符号整数类型。 该 `parallel_for` 算法还可确保指定的范围不会溢出已签名的类型。 OpenMP 版本2.0 和2.5 仅允许已签名的整型索引类型。 OpenMP 也不验证索引范围。

此示例中使用并发运行时的版本还使用 [Concurrency：：可组合](../../parallel/concrt/reference/combinable-class.md) 对象代替 [原子](../openmp/reference/openmp-directives.md#atomic) 指令来递增计数器值，而无需同步。

有关 `parallel_for` 和其他并行算法的详细信息，请参阅 [并行算法](../../parallel/concrt/parallel-algorithms.md)。 有关类的详细信息 `combinable` ，请参阅 [并行容器和对象](../../parallel/concrt/parallel-containers-and-objects.md)。

## <a name="example---use-stdarray"></a>示例-使用 std：： array

此示例修改了上一个，以对 [std：： array](../../standard-library/array-class-stl.md) 对象而不是在本机数组上执行操作。 由于 OpenMP 版本2.0 和2.5 只允许在构造中使用有符号整数索引类型 `parallel_for` ，因此不能使用迭代器并行访问 c + + 标准库容器的元素。 并行模式库 (PPL) 提供 [并发性：:p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) 算法，该算法并行执行任务（如 c + + 标准库提供的迭代容器）。 它使用算法使用的相同分区逻辑 `parallel_for` 。 `parallel_for_each`算法类似于 c + + 标准库[std：： for_each](../../standard-library/algorithm-functions.md#for_each)算法，只不过 `parallel_for_each` 算法并发执行任务。

[!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]

## <a name="compiling-the-code"></a>编译代码

复制代码示例并将其粘贴到 Visual Studio 项目中，或粘贴到一个名为的文件中， `concrt-omp-count-primes.cpp` 然后在 Visual Studio 命令提示符窗口中运行以下命令。

> **cl.exe/EHsc/openmp concrt-omp-count-primes**

## <a name="see-also"></a>请参阅

[从 OpenMP 迁移至并发运行时](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[并行算法](../../parallel/concrt/parallel-algorithms.md)<br/>
[并行容器和对象](../../parallel/concrt/parallel-containers-and-objects.md)
