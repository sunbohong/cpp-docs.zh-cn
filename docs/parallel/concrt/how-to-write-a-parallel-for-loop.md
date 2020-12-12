---
description: 了解详细信息：如何：编写 parallel_for 循环
title: 如何：编写 parallel_for 循环
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel_for loop [Concurrency Runtime]
- parallel_for function, example
ms.assetid: adb4d64e-5514-4b70-8dcb-b9210e6b5a1c
ms.openlocfilehash: ccf66c3e457b540721f0a76722b9d17206cf0f7f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205689"
---
# <a name="how-to-write-a-parallel_for-loop"></a>如何：编写 parallel_for 循环

此示例演示如何使用 [concurrency：:p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) 来计算两个矩阵的乘积。

## <a name="example-compute-the-product-of-two-matrices"></a>示例：计算两个矩阵的乘积

下面的示例演示了 `matrix_multiply` 用于计算两个正方形矩阵的乘积的函数。

[!code-cpp[concrt-parallel-matrix-multiply#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_1.cpp)]

## <a name="example-compute-a-matrix-multiply-in-parallel"></a>示例：计算矩阵并行

下面的示例演示了一个 `parallel_matrix_multiply` 函数，该函数使用 `parallel_for` 算法并行执行外部循环。

[!code-cpp[concrt-parallel-matrix-multiply#2](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_2.cpp)]

此示例并行外部循环，这只是因为它执行的工作足以从并行处理的开销中获益。 如果并行化内部循环，则不会获得性能提高，因为内部循环执行的少量工作不会克服并行处理的开销。 因此，仅并行化外部循环是在大多数系统上最大程度地发挥并发优势的最佳方式。

## <a name="example-finished-parallel_for-loop-code-sample"></a>示例：已完成 parallel_for 循环代码示例

下面更完整的示例将函数的性能 `matrix_multiply` 与函数进行比较 `parallel_matrix_multiply` 。

[!code-cpp[concrt-parallel-matrix-multiply#3](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-loop_3.cpp)]

以下是具有四个处理器的计算机的输出示例。

```Output
serial: 3853
parallel: 1311
```

## <a name="compiling-the-code"></a>编译代码

若要编译代码，请复制代码，然后将其粘贴到 Visual Studio 项目中，或粘贴到一个名为的文件中， `parallel-matrix-multiply.cpp` 然后在 Visual Studio 命令提示符窗口中运行以下命令。

> **cl.exe/EHsc parallel-matrix-multiply**

## <a name="see-also"></a>请参阅

[并行算法](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_for 函数](reference/concurrency-namespace-functions.md#parallel_for)
