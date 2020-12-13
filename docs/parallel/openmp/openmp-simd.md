---
description: 了解详细信息： SIMD 扩展
title: SIMD 扩展
ms.date: 03/20/2019
helpviewer_keywords:
- SIMD
- OpenMP in Visual C++, new features
- explicit parallelization, new features
ms.openlocfilehash: 58a3f29002c4e517a2019454dfe741dfb5352a3e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342421"
---
# <a name="simd-extension"></a>SIMD 扩展

Visual C++ 当前支持 OpenMP 2.0 标准，但 Visual Studio 2019 现在还提供了 SIMD 功能。

> [!NOTE]
> 若要使用 SIMD，请使用开关进行编译， `-openmp:experimental` 使其他 OpenMP 功能在使用开关时不可用 `-openmp` 。
>
> `-openmp:experimental`交换机 subsumes `-openmp` ，这意味着所有 OpenMP 2.0 功能都包含在其使用中。

有关详细信息，请参阅 [Visual Studio 中的 SIMD c + + OpenMP 扩展](https://devblogs.microsoft.com/cppblog/simd-extension-to-c-openmp-in-visual-studio/)。

## <a name="openmp-simd-in-visual-c"></a>Visual C++ 中的 OpenMP SIMD

Openmp SIMD （OpenMP 4.0 标准中引入）的目标是进行向量友好循环。 通过在 `simd` 循环之前使用指令，编译器可以忽略矢量依赖关系，使循环尽可能实现矢量友好，并尊重用户对同时执行多个循环迭代的意图。

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

Visual C++ 提供类似的非 OpenMP 循环杂注（如 `#pragma vector` 和 `#pragma ivdep` ），但对于 OpenMP SIMD，编译器可以执行更多操作，例如：

- 始终允许忽略现有矢量依赖项。
- `/fp:fast` 在循环内启用。
- 带函数调用的外部循环和循环是向量友好的。
- 嵌套循环可以合并为一个循环，并使向量更好。
- 使用的混合加速 `#pragma omp for simd` 实现了粗粒度的多线程和精细矢量。  

对于向量友好循环，编译器将保持无提示，除非使用向量支持日志开关：

```cmd
    cl -O2 -openmp:experimental -Qvec-report:2 mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(96) : info C5001: Omp simd loop vectorized
```

对于非向量友好循环，编译器会发出每条消息：

```cmd
    cl -O2 -openmp:experimental mycode.cpp
```

```Output
    mycode.cpp(84) : info C5002: Omp simd loop not vectorized due to reason '1200'
    mycode.cpp(90) : info C5002: Omp simd loop not vectorized due to reason '1200'
```

### <a name="clauses"></a>子句

OpenMP SIMD 指令还可以采用以下子句来增强矢量支持：

|指令|描述|
|---|---|
|`simdlen(length)`|指定向量通道数。|
|`safelen(length)`|指定矢量依赖关系距离。|
|`linear(list[ : linear-step]`)|从循环感应变量到数组订阅的线性映射。|
|`aligned(list[ : alignment])`|数据的对齐方式。|
|`private(list)`|指定数据私有化。|
|`lastprivate(list)`|指定包含上一次迭代的最终值的数据私有化。|
|`reduction(reduction-identifier:list)`|指定自定义缩减运算。|
|`collapse(n)`|合并循环嵌套。|

> [!NOTE]
> 编译器会对非有效的 SIMD 子句进行分析和忽略，并发出警告。
>
> 例如，使用以下代码会发出警告：
>
> ```c
>    #pragma omp simd simdlen(8)
>    for (i = 0; i < count; i++)
>    {
>        a[i] = a[i-1] + 1;
>        b[i] = *c + 1;
>        bar(i);
>    }
> ```
>
> ```Output
>    warning C4849: OpenMP 'simdlen' clause ignored in 'simd' directive
> ```

### <a name="example"></a>示例
  
OpenMP SIMD 指令为用户提供了一种方法，用于指示编译器使循环具有更好的矢量。 通过使用 OpenMP SIMD 指令批注循环，用户希望同时执行多个循环迭代。

例如，下面的循环用 OpenMP SIMD 指令进行批注。 循环迭代之间没有完全的并行性，因为存在从 [i] 到 a [i-1] 的反向依赖项，但由于 SIMD 指令的原因，编译器仍允许将第一条语句的连续迭代打包为一个向量指令并并行运行它们。

```c
    #pragma omp simd
    for (i = 0; i < count; i++)
    {
        a[i] = a[i-1] + 1;
        b[i] = *c + 1;
        bar(i);
    }
```

因此，以下转换后的矢量形式是 **合法** 的，因为编译器会保留每个原始循环迭代的顺序行为。 换句话说，在 `a[i]` 之后执行，在 `a[-1]` 之后执行，最后对 `b[i]` `a[i]` 的调用 `bar` 发生。

```c
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        b[i:i+3] = *c + 1;
        bar(i);
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

如果它可以与或别名，则 **不合法** 地将内存引用移 `*c` 出循环 `a[i]` `b[i]` 。 如果语句中断了顺序依赖关系，则在一个原始迭代内对它们重新排序也不合法。 例如，以下转换循环不合法：

```c
    c = b;
    t = *c;
    for (i = 0; i < count; i+=4)
    {
        a[i:i+3] = a[i-1:i+2] + 1;
        bar(i);            // illegal to reorder if bar[i] depends on b[i]
        b[i:i+3] = t + 1;  // illegal to move *c out of the loop
        bar(i+1);
        bar(i+2);
        bar(i+3);
    }
```

## <a name="see-also"></a>请参阅

[/openmp (Enable OpenMP 2.0 支持) ](../../build/reference/openmp-enable-openmp-2-0-support.md)<br/>
