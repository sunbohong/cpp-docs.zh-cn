---
title: 从 OpenMP 迁移至并发运行时
ms.date: 11/04/2016
helpviewer_keywords:
- Concurrency Runtime, migrating from OpenMP
- OpenMP, migrating to the Concurrency Runtime
ms.assetid: 9bab7bb1-e45d-44b2-8509-3b226be2c93b
ms.openlocfilehash: 081d0ae8b312d827a0af98dd45c62f7563e81677
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507762"
---
# <a name="migrating-from-openmp-to-the-concurrency-runtime"></a>从 OpenMP 迁移至并发运行时

并发运行时支持各种编程模型。 这些模型可能会与其他库的模型重叠或对其进行补充。 本部分中的文档将 [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp) 与并发运行时进行比较，并提供有关如何迁移现有 OpenMP 代码以使用并发运行时的示例。

OpenMP 编程模型由开放标准定义，具有与 Fortran 和 C/C++ 编程语言定义完善的绑定。 Microsoft c + + 编译器支持的 OpenMP 版本2.0 和2.5 非常适合用于迭代的并行算法;也就是说，它们在数据数组上执行并行迭代。 OpenMP 3.0 除了迭代任务外，还支持非重复任务。

当预设了并行度，并匹配了系统上的可用资源时，OpenMP 的效率最高。 OpenMP 模型非常适合于高性能计算，在这种情况下，在一台计算机的处理资源中分布很大的计算问题。 在此方案中，硬件环境通常是固定的，开发人员可合理地期望在执行该算法时拥有对所有计算资源的独占访问权限。

但是，不太受约束的计算环境可能不是 OpenMP 的最佳匹配项。 例如，递归问题 (如快速排序算法或搜索数据树) 使用 OpenMP 2.0 和2.5 来实现更难。 并发运行时通过提供 [异步代理库](../../parallel/concrt/asynchronous-agents-library.md) 和 [并行模式库](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL) ，对 OpenMP 的功能进行了补充。 异步代理库支持粗粒度的任务并行度;PPL 支持更细化的并行任务。 并发运行时提供了并行执行操作所需的基础结构，以便你可以专注于应用程序的逻辑。 不过，由于并发运行时支持多种编程模型，因此其计划开销可能大于其他并发库，如 OpenMP。 因此，建议在转换现有 OpenMP 代码以使用并发运行时时，以增量方式测试性能。

## <a name="when-to-migrate-from-openmp-to-the-concurrency-runtime"></a>何时从 OpenMP 迁移到并发运行时

在以下情况下，最好将现有 OpenMP 代码迁移到使用并发运行时。

|案例|并发运行时的优点|
|-----------|-------------------------------------------|
|需要可扩展的并发编程框架。|并发运行时中的许多功能均可扩展。 还可以结合现有功能来构造新功能。 由于 OpenMP 依赖于编译器指令，因此无法轻松地对其进行扩展。|
|你的应用程序将从协作式阻止中获益。|当任务阻止，因为它需要尚不可用的资源时，并发运行时可以在第一个任务等待资源时执行其他任务。|
|你的应用程序将受益于动态负载平衡。|并发运行时使用计划算法，在工作负荷更改时调整计算资源的分配。 在 OpenMP 中，当计划程序将计算资源分配到并行区域时，这些资源分配在整个计算中都是固定的。|
|需要异常处理支持。|PPL 使你可以在并行区域或循环的内部和外部捕获异常。 在 OpenMP 中，必须在并行区域或循环中处理异常。|
|需要取消机制。|PPL 使应用程序可以取消单个任务和并行工作树。 OpenMP 要求应用程序实现其自己的取消机制。|
|需要并行代码在从其开始的不同上下文中完成。|并发运行时使你可以在一个上下文中启动任务，然后在另一个上下文中等待或取消该任务。 在 OpenMP 中，所有并行工作都必须在启动它的上下文中完成。|
|需要增强的调试支持。|Visual Studio 提供了 " **并行堆栈** " 和 " **并行任务** " 窗口，以便你可以更轻松地调试多线程应用程序。<br /><br /> 有关对并发运行时的调试支持的详细信息，请参阅 [使用 "任务" 窗口](/visualstudio/debugger/using-the-tasks-window)、 [使用 "并行堆栈" 窗口](/visualstudio/debugger/using-the-parallel-stacks-window)以及 [演练：调试并行应用程序](/visualstudio/debugger/walkthrough-debugging-a-parallel-application)。|

## <a name="when-not-to-migrate-from-openmp-to-the-concurrency-runtime"></a>何时不从 OpenMP 迁移到并发运行时

以下情况描述了在将现有 OpenMP 代码迁移到使用并发运行时时可能不适合的情况。

|案例|说明|
|-----------|-----------------|
|你的应用程序已满足你的要求。|如果对应用程序性能和当前调试支持感到满意，则可能不适合迁移。|
|并行循环体执行的操作很少。|并发运行时任务计划程序的开销可能并不能克服并行执行循环体的好处，尤其是当循环体相对较小时。|
|您的应用程序以 C 编写。|由于并发运行时使用许多 c + + 功能，因此当你无法编写允许 C 应用程序完全使用它的代码时，它可能不适合。|

## <a name="related-topics"></a>相关主题

[如何：转换 OpenMP parallel for 循环以使用并发运行时](../../parallel/concrt/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime.md)

给定一个使用 OpenMP [并行](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) 和 [for](../openmp/reference/openmp-directives.md#for-openmp) 指令的基本循环，演示如何将其转换为使用并发运行时 [Concurrency：:p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) 算法。

[如何：转换使用取消的 OpenMP 循环以使用并发运行时](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)<br/>
给定一个 OpenMP [并行](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[for](../openmp/reference/openmp-directives.md#for-openmp) 循环，无需运行所有迭代，演示了如何将其转换为使用并发运行时取消机制。

[如何：转换使用异常处理的 OpenMP 循环以使用并发运行时](../../parallel/concrt/convert-an-openmp-loop-that-uses-exception-handling.md)<br/>
对于执行异常处理的 OpenMP [并行](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[for](../openmp/reference/openmp-directives.md#for-openmp) 循环，演示如何将其转换为使用并发运行时异常处理机制。

[如何：转换使用缩减变量的 OpenMP 循环以使用并发运行时](../../parallel/concrt/convert-an-openmp-loop-that-uses-a-reduction-variable.md)<br/>
对于使用[缩减](../openmp/reference/openmp-clauses.md#reduction)子句的 OpenMP[并行](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[for](../openmp/reference/openmp-directives.md#for-openmp)循环，演示如何将其转换为使用并发运行时。

## <a name="see-also"></a>请参阅

[并发运行时](../../parallel/concrt/concurrency-runtime.md)<br/>
[OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp)<br/>
[并行模式库 (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
[异步代理库](../../parallel/concrt/asynchronous-agents-library.md)
