---
description: 了解详细信息：如何：使用可组合的提高性能
title: 如何：使用 combinable 提高性能
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- improving parallel performance with combinable [Concurrency Runtime]
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
ms.openlocfilehash: b9ab906f00f32fee59e2dd9a1131fe87fcbc53a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283298"
---
# <a name="how-to-use-combinable-to-improve-performance"></a>如何：使用 combinable 提高性能

此示例演示如何使用 [concurrency：：可组合](../../parallel/concrt/reference/combinable-class.md) 类计算作为质数的 [std：： array](../../standard-library/array-class-stl.md) 对象中的数字之和。 `combinable`类通过消除共享状态来提高性能。

> [!TIP]
> 在某些情况下，并行映射 ([concurrency：:p arallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)) 并降低 ([concurrency：： parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)) 可提供比上更多的性能改进 `combinable` 。 有关使用 map 和化简操作生成与此示例相同的结果的示例，请参阅 [并行算法](../../parallel/concrt/parallel-algorithms.md)。

## <a name="example---accumulate"></a>示例-累积

下面的示例使用 [std：：累积](../../standard-library/numeric-functions.md#accumulate) 函数计算数组中作为质数的元素的和。 在此示例中， `a` 是一个 `array` 对象，并且 `is_prime` 函数确定其输入值是否为质数。

[!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_1.cpp)]

## <a name="example---parallel_for_each"></a>示例-parallel_for_each

下面的示例演示并行化上一个示例的一种简单方法。 此示例使用 [concurrency：:p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) 算法并行处理数组，并使用 [concurrency：： critical_section](../../parallel/concrt/reference/critical-section-class.md) 对象同步对变量的访问 `prime_sum` 。 此示例不进行缩放，因为每个线程都必须等待共享资源变为可用。

[!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_2.cpp)]

## <a name="example---combinable"></a>示例-组合

下面的示例使用 `combinable` 对象来改善上一个示例的性能。 此示例无需同步对象;它可进行缩放，因为 `combinable` 对象允许每个线程单独执行其任务。

`combinable`对象通常在两个步骤中使用。 首先，通过并行执行工作，生成一系列细化计算。 接下来，将计算)  (或减少为最终结果。 此示例使用 [concurrency：：可组合：： local](reference/combinable-class.md#local) 方法获取对本地和的引用。 然后，它使用 [concurrency：：可组合](reference/combinable-class.md#combine) 方法和 [std：:p lu](../../standard-library/plus-struct.md) 对象将本地计算合并为最终结果。

[!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_3.cpp)]

## <a name="example---serial-and-parallel"></a>示例-串行和并行

下面的完整示例将按串行方式和并行方式计算质数的总和。 该示例将执行两个计算所需的时间打印到控制台。

[!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_4.cpp)]

以下是具有四个处理器的计算机的输出示例。

```Output
1709600813
serial time: 6178 ms

1709600813
parallel time: 1638 ms
```

## <a name="compiling-the-code"></a>编译代码

若要编译代码，请复制代码，然后将其粘贴到 Visual Studio 项目中，或粘贴到一个名为的文件中， `parallel-sum-of-primes.cpp` 然后在 Visual Studio 命令提示符窗口中运行以下命令。

> **cl.exe/EHsc parallel-sum-of-primes**

## <a name="robust-programming"></a>可靠编程

有关使用 map 和化简操作生成相同结果的示例，请参阅 [并行算法](../../parallel/concrt/parallel-algorithms.md)。

## <a name="see-also"></a>请参阅

[并行容器和对象](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[组合类](../../parallel/concrt/reference/combinable-class.md)<br/>
[critical_section 类](../../parallel/concrt/reference/critical-section-class.md)
