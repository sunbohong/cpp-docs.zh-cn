---
description: 了解详细信息： OpenMP 环境变量
title: OpenMP 环境变量
ms.date: 03/20/2019
f1_keywords:
- OpenMP environment variables
- OMP_DYNAMIC
- OMP_NESTED
- OMP_NUM_THREADS
- OMP_SCHEDULE
helpviewer_keywords:
- OpenMP environment variables
- OMP_DYNAMIC OpenMP environment variable
- OMP_NESTED OpenMP environment variable
- OMP_NUM_THREADS OpenMP environment variable
- OMP_SCHEDULE OpenMP environment variable
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
ms.openlocfilehash: 58ca563033906f4e5e7e9d59089dc463396aa91c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342382"
---
# <a name="openmp-environment-variables"></a>OpenMP 环境变量

提供 OpenMP API 中使用的环境变量的链接。

OpenMP 标准的 Visual C++ 实现包括以下环境变量。 这些环境变量将在程序启动时读取，在运行时将忽略对其值的修改 (例如，使用 [_putenv，_wputenv](../../../c-runtime-library/reference/putenv-wputenv.md)) 。

|环境变量|说明|
|--------------------|-----------|
|[OMP_SCHEDULE](#omp-schedule)|当[](openmp-clauses.md#schedule) `schedule(runtime)` 在或指令中指定时，修改 schedule 子句的 `for` 行为 `parallel for` 。|
|[OMP_NUM_THREADS](#omp-num-threads)|设置并行区域中的最大线程数，除非由 [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) 或 [num_threads](openmp-clauses.md#num-threads)重写。|
|[OMP_DYNAMIC](#omp-dynamic)|指定 OpenMP 运行时是否可以调整并行区域中的线程数。|
|[OMP_NESTED](#omp-nested)|指定是否启用嵌套并行，除非启用或禁用了嵌套并行机制 `omp_set_nested` 。|

## <a name="omp_dynamic"></a><a name="omp-dynamic"></a> OMP_DYNAMIC

指定 OpenMP 运行时是否可以调整并行区域中的线程数。

```cmd
set OMP_DYNAMIC[=TRUE | =FALSE]
```

### <a name="remarks"></a>备注

`OMP_DYNAMIC` [Omp_set_dynamic](openmp-functions.md#omp-set-dynamic)函数可以重写环境变量。

OpenMP 标准的 Visual C++ 实现中的默认值为 `OMP_DYNAMIC=FALSE` 。

有关详细信息，请参阅 [4.3 OMP_DYNAMIC](../4-environment-variables.md#43-omp_dynamic)。

### <a name="example"></a>示例

以下命令将 `OMP_DYNAMIC` 环境变量设置为 TRUE：

```cmd
set OMP_DYNAMIC=TRUE
```

以下命令显示环境变量的当前设置 `OMP_DYNAMIC` ：

```cmd
set OMP_DYNAMIC
```

## <a name="omp_nested"></a><a name="omp-nested"></a> OMP_NESTED

指定是否启用嵌套并行，除非启用或禁用了嵌套并行机制 `omp_set_nested` 。

```cmd
set OMP_NESTED[=TRUE | =FALSE]
```

### <a name="remarks"></a>备注

`OMP_NESTED` [Omp_set_nested](openmp-functions.md#omp-set-nested)函数可以重写环境变量。

OpenMP 标准的 Visual C++ 实现中的默认值为 `OMP_DYNAMIC=FALSE` 。

有关详细信息，请参阅 [4.4 OMP_NESTED](../4-environment-variables.md#44-omp_nested)。

### <a name="example"></a>示例

以下命令将 `OMP_NESTED` 环境变量设置为 TRUE：

```cmd
set OMP_NESTED=TRUE
```

以下命令显示环境变量的当前设置 `OMP_NESTED` ：

```cmd
set OMP_NESTED
```

## <a name="omp_num_threads"></a><a name="omp-num-threads"></a> OMP_NUM_THREADS

设置并行区域中的最大线程数，除非由 [omp_set_num_threads](openmp-functions.md#omp-set-num-threads) 或 [num_threads](openmp-clauses.md#num-threads)重写。

```cmd
set OMP_NUM_THREADS[=num]
```

### <a name="parameters"></a>parameters

*编号*<br/>
并行区域中所需的最大线程数，最大为64，Visual C++ 实现。

### <a name="remarks"></a>备注

`OMP_NUM_THREADS`可以通过[omp_set_num_threads](openmp-functions.md#omp-set-num-threads)函数或[num_threads](openmp-clauses.md#num-threads)来重写环境变量。

`num`OpenMP 标准的 Visual C++ 实现中的默认值是虚拟处理器的数量，包括超线程 cpu。

有关详细信息，请参阅 [4.2 OMP_NUM_THREADS](../4-environment-variables.md#42-omp_num_threads)。

### <a name="example"></a>示例

以下命令将 `OMP_NUM_THREADS` 环境变量设置为 `16` ：

```cmd
set OMP_NUM_THREADS=16
```

以下命令显示环境变量的当前设置 `OMP_NUM_THREADS` ：

```cmd
set OMP_NUM_THREADS
```

## <a name="omp_schedule"></a><a name="omp-schedule"></a> OMP_SCHEDULE

当[](openmp-clauses.md#schedule) `schedule(runtime)` 在或指令中指定时，修改 schedule 子句的 `for` 行为 `parallel for` 。

```cmd
set OMP_SCHEDULE[=type[,size]]
```

### <a name="parameters"></a>parameters

*大小*<br/>
 (可选) 指定迭代的大小。 *大小* 必须为正整数。 默认值为 `1` ，但当 *类型* 为 static 时除外。 当 *类型* 为时无效 `runtime` 。

type<br/>
计划的类型，为 `dynamic` 、、 `guided` `runtime` 或 `static` 。

### <a name="remarks"></a>备注

OpenMP 标准的 Visual C++ 实现中的默认值为 `OMP_SCHEDULE=static,0` 。

有关详细信息，请参阅 [4.1 OMP_SCHEDULE](../4-environment-variables.md#41-omp_schedule)。

### <a name="example"></a>示例

以下命令设置 `OMP_SCHEDULE` 环境变量：

```cmd
set OMP_SCHEDULE="guided,2"
```

以下命令显示环境变量的当前设置 `OMP_SCHEDULE` ：

```cmd
set OMP_SCHEDULE
```
