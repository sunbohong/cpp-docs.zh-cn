---
title: OpenMP 子句
ms.date: 03/20/2019
f1_keywords:
- OpenMP clauses
- copyin
- copyprivate
- default
- firstprivate
- lastprivate
- nowait
- num_threads
- ordered
- private
- reduction
- schedule
- shared
helpviewer_keywords:
- OpenMP clauses
- copyin OpenMP clause
- copyprivate OpenMP clause
- default OpenMP clause
- defaults, OpenMP clause
- firstprivate OpenMP clause
- if OpenMP clause
- lastprivate OpenMP clause
- nowait OpenMP clause
- num_threads OpenMP clause
- ordered OpenMP clause
- private OpenMP clause
- reduction OpenMP clause
- schedule OpenMP clause
- shared OpenMP clause
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
ms.openlocfilehash: 495f77003fa43922d49f2fc5203076cbf927f86f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91505934"
---
# <a name="openmp-clauses"></a>OpenMP 子句

提供 OpenMP API 中使用的子句的链接。

Visual C++ 支持以下 OpenMP 子句。

对于常规属性：

|子句|说明|
|------|-----------|
|[if](#if-openmp)|指定是应并行执行循环还是在序列中执行循环。|
|[num_threads](#num-threads)|设置线程团队中的线程数。|
|[排序](#ordered-openmp-clauses)|当在循环中使用[有序](openmp-directives.md#ordered-openmp-directives)指令时[，](openmp-directives.md#for-openmp)对 parallel 语句是必需的。|
|[schedule](#schedule)|适用于 [for](openmp-directives.md#for-openmp) 指令。|
|[nowait](#nowait)|覆盖指令中的隐式。|

对于数据共享属性：

|子句|说明|
|------|-----------|
|[private](#private-openmp)|指定每个线程都应有自己的变量实例。|
|[firstprivate](#firstprivate)|指定每个线程都应有自己的变量实例，并且应使用该变量的值初始化该变量，因为它存在于并行构造之前。|
|[lastprivate](#lastprivate)|指定将该变量的封闭上下文版本设置为等于) 或 ( # pragma 节) 的上一节中的任何线程执行最终迭代 (的私有版本。|
|[共享](#shared-openmp)|指定应在所有线程之间共享一个或多个变量。|
|[default](#default-openmp)|指定并行区域中的未区分范围的变量的行为。|
|[幅度](#reduction)|指定每个线程专用的一个或多个变量是并行区域结束时的缩减操作的主体。|
|[copyin](#copyin)|允许线程访问 [threadprivate](openmp-directives.md#threadprivate) 变量的主线程的值。|
|[copyprivate](#copyprivate)|指定应在所有线程之间共享一个或多个变量。|

## <a name="copyin"></a><a name="copyin"></a> copyin

允许线程访问 [threadprivate](openmp-directives.md#threadprivate) 变量的主线程的值。

```cpp
copyin(var)
```

### <a name="parameters"></a>参数

*var*<br/>
`threadprivate`将在主线程中用变量的值初始化的变量，因为它存在于并行构造之前。

### <a name="remarks"></a>注解

`copyin` 适用于以下指令：

- [并行](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [个](openmp-directives.md#sections-openmp)

有关详细信息，请参阅 [2.7.2.7 copyin](../2-directives.md#2727-copyin)。

### <a name="example"></a>示例

有关使用的示例，请参阅 [threadprivate](openmp-directives.md#threadprivate) `copyin` 。

## <a name="copyprivate"></a><a name="copyprivate"></a> copyprivate

指定应在所有线程之间共享一个或多个变量。

```cpp
copyprivate(var)
```

### <a name="parameters"></a>参数

*var*<br/>
要共享的一个或多个变量。 如果指定了多个变量，则用逗号分隔变量名称。

### <a name="remarks"></a>注解

`copyprivate` 适用于 [单个](openmp-directives.md#single) 指令。

有关详细信息，请参阅 [2.7.2.8 copyprivate](../2-directives.md#2728-copyprivate)。

### <a name="example"></a>示例

```cpp
// omp_copyprivate.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

float x, y, fGlobal = 1.0;
#pragma omp threadprivate(x, y)

float get_float() {
   fGlobal += 0.001;
   return fGlobal;
}

void use_float(float f, int t) {
   printf_s("Value = %f, thread = %d\n", f, t);
}

void CopyPrivate(float a, float b) {
   #pragma omp single copyprivate(a, b, x, y)
   {
      a = get_float();
      b = get_float();
      x = get_float();
      y = get_float();
    }

   use_float(a, omp_get_thread_num());
   use_float(b, omp_get_thread_num());
   use_float(x, omp_get_thread_num());
   use_float(y, omp_get_thread_num());
}

int main() {
   float a = 9.99, b = 123.456;

   printf_s("call CopyPrivate from a single thread\n");
   CopyPrivate(9.99, 123.456);

   printf_s("call CopyPrivate from a parallel region\n");
   #pragma omp parallel
   {
      CopyPrivate(a, b);
   }
}
```

```Output
call CopyPrivate from a single thread
Value = 1.001000, thread = 0
Value = 1.002000, thread = 0
Value = 1.003000, thread = 0
Value = 1.004000, thread = 0
call CopyPrivate from a parallel region
Value = 1.005000, thread = 0
Value = 1.005000, thread = 1
Value = 1.006000, thread = 0
Value = 1.006000, thread = 1
Value = 1.007000, thread = 0
Value = 1.007000, thread = 1
Value = 1.008000, thread = 0
Value = 1.008000, thread = 1
```

## <a name="default"></a><a name="default-openmp"></a> 缺省值

指定并行区域中的未区分范围的变量的行为。

```cpp
default(shared | none)
```

### <a name="remarks"></a>注解

`shared`如果 `default` 未指定子句，则表示并行区域中的任何变量都将被视为使用 [共享](#shared-openmp) 子句指定。 `none`意味着并行区域中使用的任何不属于[private](#private-openmp)、 [shared](#shared-openmp)、 [firstprivate](#firstprivate)或[lastprivate](#lastprivate)子句的[reduction](#reduction)变量都将导致编译器错误。

`default` 适用于以下指令：

- [并行](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [个](openmp-directives.md#sections-openmp)

有关详细信息，请参阅 [2.7.2.5 默认值](../2-directives.md#2725-default)。

### <a name="example"></a>示例

有关使用的示例，请参阅 [私有](#private-openmp) `default` 。

## <a name="firstprivate"></a><a name="firstprivate"></a> firstprivate

指定每个线程都应有自己的变量实例，并且应使用该变量的值初始化该变量，因为它存在于并行构造之前。

```cpp
firstprivate(var)
```

### <a name="parameters"></a>参数

*var*<br/>
要在每个线程中包含实例并将用变量的值初始化的变量，因为它存在于并行构造之前。 如果指定了多个变量，则用逗号分隔变量名称。

### <a name="remarks"></a>注解

`firstprivate` 适用于以下指令：

- [for](openmp-directives.md#for-openmp)
- [并行](openmp-directives.md#parallel)
- [个](openmp-directives.md#sections-openmp)
- single

有关详细信息，请参阅 [2.7.2.2 firstprivate](../2-directives.md#2722-firstprivate)。

### <a name="example"></a>示例

有关使用的示例 `firstprivate` ，请参阅 [私有](#private-openmp)中的示例。

## <a name="if-openmp"></a><a name="if-openmp"></a> 如果 (OpenMP) 

指定是应并行执行循环还是在序列中执行循环。

```cpp
if(expression)
```

### <a name="parameters"></a>参数

*expression*<br/>
一个整数表达式，如果计算结果为 true (非零) ，将导致并行区域中的代码并行执行。 如果表达式的计算结果为 false (零) ，则通过单个线程) 在串行 (中执行并行区域。

### <a name="remarks"></a>注解

`if` 适用于以下指令：

- [并行](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [个](openmp-directives.md#sections-openmp)

有关详细信息，请参阅 [2.3 并行构造](../2-directives.md#23-parallel-construct)。

### <a name="example"></a>示例

```cpp
// omp_if.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

void test(int val)
{
    #pragma omp parallel if (val)
    if (omp_in_parallel())
    {
        #pragma omp single
        printf_s("val = %d, parallelized with %d threads\n",
                 val, omp_get_num_threads());
    }
    else
    {
        printf_s("val = %d, serialized\n", val);
    }
}

int main( )
{
    omp_set_num_threads(2);
    test(0);
    test(2);
}
```

```Output
val = 0, serialized
val = 2, parallelized with 2 threads
```

## <a name="lastprivate"></a><a name="lastprivate"></a> lastprivate

指定将该变量的封闭上下文版本设置为等于) 或 ( # pragma 节) 的上一节中的任何线程执行最终迭代 (的私有版本。

```cpp
lastprivate(var)
```

### <a name="parameters"></a>参数

*var*<br/>
设置为等于) 或 ( # pragma 节) 的最后一个部分的任何线程执行最终 (迭代的私有版本的变量。

### <a name="remarks"></a>注解

`lastprivate` 适用于以下指令：

- [for](openmp-directives.md#for-openmp)
- [个](openmp-directives.md#sections-openmp)

有关详细信息，请参阅 [2.7.2.3 lastprivate](../2-directives.md#2723-lastprivate)。

### <a name="example"></a>示例

有关 using 子句的示例，请参阅 [计划](#schedule) `lastprivate` 。

## <a name="nowait"></a><a name="nowait"></a> nowait

覆盖指令中的隐式。

```cpp
nowait
```

### <a name="remarks"></a>注解

`nowait` 适用于以下指令：

- [for](openmp-directives.md#for-openmp)
- [个](openmp-directives.md#sections-openmp)
- single

有关详细信息，请参阅 [2.4.1 for 构造](../2-directives.md#241-for-construct)、 [2.4.2 sections 节构造](../2-directives.md#242-sections-construct)和 [2.4.3 单一构造](../2-directives.md#243-single-construct)。

### <a name="example"></a>示例

```cpp
// omp_nowait.cpp
// compile with: /openmp /c
#include <stdio.h>

#define SIZE 5

void test(int *a, int *b, int *c, int size)
{
    int i;
    #pragma omp parallel
    {
        #pragma omp for nowait
        for (i = 0; i < size; i++)
            b[i] = a[i] * a[i];

        #pragma omp for nowait
        for (i = 0; i < size; i++)
            c[i] = a[i]/2;
    }
}

int main( )
{
    int a[SIZE], b[SIZE], c[SIZE];
    int i;

    for (i=0; i<SIZE; i++)
        a[i] = i;

    test(a,b,c, SIZE);

    for (i=0; i<SIZE; i++)
        printf_s("%d, %d, %d\n", a[i], b[i], c[i]);
}
```

```Output
0, 0, 0
1, 1, 0
2, 4, 1
3, 9, 1
4, 16, 2
```

## <a name="num_threads"></a><a name="num-threads"></a> num_threads

设置线程团队中的线程数。

```cpp
num_threads(num)
```

### <a name="parameters"></a>参数

*num*<br/>
线程数

### <a name="remarks"></a>注解

`num_threads`子句具有与[omp_set_num_threads](openmp-functions.md#omp-set-num-threads)函数相同的功能。

`num_threads` 适用于以下指令：

- [并行](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [个](openmp-directives.md#sections-openmp)

有关详细信息，请参阅 [2.3 并行构造](../2-directives.md#23-parallel-construct)。

### <a name="example"></a>示例

有关 using 子句的示例，请参阅 [并行](openmp-directives.md#parallel) `num_threads` 。

## <a name="ordered"></a><a name="ordered-openmp-clauses"></a> 排序

当在循环中使用[有序](openmp-directives.md#ordered-openmp-directives)指令时[，](openmp-directives.md#for-openmp)对 parallel 语句是必需的。

```cpp
ordered
```

### <a name="remarks"></a>注解

`ordered` 适用于 [for](openmp-directives.md#for-openmp) 指令。

有关详细信息，请参阅 [2.4.1 for 构造](../2-directives.md#241-for-construct)。

### <a name="example"></a>示例

有关 using 子句的示例，请参阅已 [排序](openmp-directives.md#ordered-openmp-directives) `ordered` 。

## <a name="private"></a><a name="private-openmp"></a> 专有

指定每个线程都应有自己的变量实例。

```cpp
private(var)
```

### <a name="parameters"></a>参数

*var*<br/>
要在每个线程中包含实例的变量。

### <a name="remarks"></a>注解

`private` 适用于以下指令：

- [for](openmp-directives.md#for-openmp)
- [并行](openmp-directives.md#parallel)
- [个](openmp-directives.md#sections-openmp)
- single

有关详细信息，请参阅 [2.7.2.1 private](../2-directives.md#2721-private)。

### <a name="example"></a>示例

```c
// openmp_private.c
// compile with: /openmp
#include <windows.h>
#include <assert.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SLEEP_THREAD 1
#define NUM_LOOPS 2

enum Types {
   ThreadPrivate,
   Private,
   FirstPrivate,
   LastPrivate,
   Shared,
   MAX_TYPES
};

int nSave[NUM_THREADS][MAX_TYPES][NUM_LOOPS] = {{0}};
int nThreadPrivate;

#pragma omp threadprivate(nThreadPrivate)
#pragma warning(disable:4700)

int main() {
   int nPrivate = NUM_THREADS;
   int nFirstPrivate = NUM_THREADS;
   int nLastPrivate = NUM_THREADS;
   int nShared = NUM_THREADS;
   int nRet = 0;
   int i;
   int j;
   int nLoop = 0;

   nThreadPrivate = NUM_THREADS;
   printf_s("These are the variables before entry "
           "into the parallel region.\n");
   printf_s("nThreadPrivate = %d\n", nThreadPrivate);
   printf_s("      nPrivate = %d\n", nPrivate);
   printf_s(" nFirstPrivate = %d\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d\n", nLastPrivate);
   printf_s("       nShared = %d\n\n", nShared);
   omp_set_num_threads(NUM_THREADS);

   #pragma omp parallel copyin(nThreadPrivate) private(nPrivate) shared(nShared) firstprivate(nFirstPrivate)
   {
      #pragma omp for schedule(static) lastprivate(nLastPrivate)
      for (i = 0 ; i < NUM_THREADS ; ++i) {
         for (j = 0 ; j < NUM_LOOPS ; ++j) {
            int nThread = omp_get_thread_num();
            assert(nThread < NUM_THREADS);

            if (nThread == SLEEP_THREAD)
               Sleep(100);
            nSave[nThread][ThreadPrivate][j] = nThreadPrivate;
            nSave[nThread][Private][j] = nPrivate;
            nSave[nThread][Shared][j] = nShared;
            nSave[nThread][FirstPrivate][j] = nFirstPrivate;
            nSave[nThread][LastPrivate][j] = nLastPrivate;
            nThreadPrivate = nThread;
            nPrivate = nThread;
            nShared = nThread;
            nLastPrivate = nThread;
            --nFirstPrivate;
         }
      }
   }

   for (i = 0 ; i < NUM_LOOPS ; ++i) {
      for (j = 0 ; j < NUM_THREADS ; ++j) {
         printf_s("These are the variables at entry of "
                  "loop %d of thread %d.\n", i + 1, j);
         printf_s("nThreadPrivate = %d\n",
                  nSave[j][ThreadPrivate][i]);
         printf_s("      nPrivate = %d\n",
                  nSave[j][Private][i]);
         printf_s(" nFirstPrivate = %d\n",
                  nSave[j][FirstPrivate][i]);
         printf_s("  nLastPrivate = %d\n",
                  nSave[j][LastPrivate][i]);
         printf_s("       nShared = %d\n\n",
                  nSave[j][Shared][i]);
      }
   }

   printf_s("These are the variables after exit from "
            "the parallel region.\n");
   printf_s("nThreadPrivate = %d (The last value in the "
            "master thread)\n", nThreadPrivate);
   printf_s("      nPrivate = %d (The value prior to "
            "entering parallel region)\n", nPrivate);
   printf_s(" nFirstPrivate = %d (The value prior to "
            "entering parallel region)\n", nFirstPrivate);
   printf_s("  nLastPrivate = %d (The value from the "
            "last iteration of the loop)\n", nLastPrivate);
   printf_s("       nShared = %d (The value assigned, "
            "from the delayed thread, %d)\n\n",
            nShared, SLEEP_THREAD);
}
```

```Output
These are the variables before entry into the parallel region.
nThreadPrivate = 4
      nPrivate = 4
nFirstPrivate = 4
  nLastPrivate = 4
       nShared = 4

These are the variables at entry of loop 1 of thread 0.
nThreadPrivate = 4
      nPrivate = 1310720
nFirstPrivate = 4
  nLastPrivate = 1245104
       nShared = 3

These are the variables at entry of loop 1 of thread 1.
nThreadPrivate = 4
      nPrivate = 4488
nFirstPrivate = 4
  nLastPrivate = 19748
       nShared = 0

These are the variables at entry of loop 1 of thread 2.
nThreadPrivate = 4
      nPrivate = -132514848
nFirstPrivate = 4
  nLastPrivate = -513199792
       nShared = 4

These are the variables at entry of loop 1 of thread 3.
nThreadPrivate = 4
      nPrivate = 1206
nFirstPrivate = 4
  nLastPrivate = 1204
       nShared = 2

These are the variables at entry of loop 2 of thread 0.
nThreadPrivate = 0
      nPrivate = 0
nFirstPrivate = 3
  nLastPrivate = 0
       nShared = 0

These are the variables at entry of loop 2 of thread 1.
nThreadPrivate = 1
      nPrivate = 1
nFirstPrivate = 3
  nLastPrivate = 1
       nShared = 1

These are the variables at entry of loop 2 of thread 2.
nThreadPrivate = 2
      nPrivate = 2
nFirstPrivate = 3
  nLastPrivate = 2
       nShared = 2

These are the variables at entry of loop 2 of thread 3.
nThreadPrivate = 3
      nPrivate = 3
nFirstPrivate = 3
  nLastPrivate = 3
       nShared = 3

These are the variables after exit from the parallel region.
nThreadPrivate = 0 (The last value in the master thread)
      nPrivate = 4 (The value prior to entering parallel region)
nFirstPrivate = 4 (The value prior to entering parallel region)
  nLastPrivate = 3 (The value from the last iteration of the loop)
       nShared = 1 (The value assigned, from the delayed thread, 1)
```

## <a name="reduction"></a><a name="reduction"></a> 幅度

指定每个线程专用的一个或多个变量是并行区域结束时的缩减操作的主体。

```cpp
reduction(operation:var)
```

### <a name="parameters"></a>参数

*operation*<br/>
操作的运算符，该运算符用于对并行区域末尾的变量 *var* 执行操作。

*var*<br/>
要对其进行标量缩减的一个或多个变量。 如果指定了多个变量，则用逗号分隔变量名称。

### <a name="remarks"></a>注解

`reduction` 适用于以下指令：

- [并行](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [个](openmp-directives.md#sections-openmp)

有关详细信息，请参阅 [2.7.2.6 缩减](../2-directives.md#2726-reduction)。

### <a name="example"></a>示例

```cpp
// omp_reduction.cpp
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define SUM_START   1
#define SUM_END     10
#define FUNC_RETS   {1, 1, 1, 1, 1}

int bRets[5] = FUNC_RETS;
int nSumCalc = ((SUM_START + SUM_END) * (SUM_END - SUM_START + 1)) / 2;

int func1( ) {return bRets[0];}
int func2( ) {return bRets[1];}
int func3( ) {return bRets[2];}
int func4( ) {return bRets[3];}
int func5( ) {return bRets[4];}

int main( )
{
    int nRet = 0,
        nCount = 0,
        nSum = 0,
        i,
        bSucceed = 1;

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel reduction(+ : nCount)
    {
        nCount += 1;

        #pragma omp for reduction(+ : nSum)
        for (i = SUM_START ; i <= SUM_END ; ++i)
            nSum += i;

        #pragma omp sections reduction(&& : bSucceed)
        {
            #pragma omp section
            {
                bSucceed = bSucceed && func1( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func2( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func3( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func4( );
            }

            #pragma omp section
            {
                bSucceed = bSucceed && func5( );
            }
        }
    }

    printf_s("The parallel section was executed %d times "
             "in parallel.\n", nCount);
    printf_s("The sum of the consecutive integers from "
             "%d to %d, is %d\n", 1, 10, nSum);

    if (bSucceed)
        printf_s("All of the functions, func1 through "
                 "func5 succeeded!\n");
    else
        printf_s("One or more of the functions, func1 "
                 "through func5 failed!\n");

    if (nCount != NUM_THREADS)
    {
        printf_s("ERROR: For %d threads, %d were counted!\n",
                 NUM_THREADS, nCount);
        nRet |= 0x1;
   }

    if (nSum != nSumCalc)
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                "but %d was reported!\n",
                SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x10;
    }

    if (bSucceed != (bRets[0] && bRets[1] &&
                     bRets[2] && bRets[3] && bRets[4]))
    {
        printf_s("ERROR: The sum of %d through %d should be %d, "
                 "but %d was reported!\n",
                 SUM_START, SUM_END, nSumCalc, nSum);
        nRet |= 0x100;
    }
}
```

```Output
The parallel section was executed 4 times in parallel.
The sum of the consecutive integers from 1 to 10, is 55
All of the functions, func1 through func5 succeeded!
```

## <a name="schedule"></a><a name="schedule"></a> 编制

适用于 [for](openmp-directives.md#for-openmp) 指令。

```cpp
schedule(type[,size])
```

### <a name="parameters"></a>参数

type<br/>
计划的类型，为 `dynamic` 、、 `guided` `runtime` 或 `static` 。

*大小*<br/>
 (可选) 指定迭代的大小。 *大小* 必须为整数。 当 *类型* 为时无效 `runtime` 。

### <a name="remarks"></a>注解

有关详细信息，请参阅 [2.4.1 for 构造](../2-directives.md#241-for-construct)。

### <a name="example"></a>示例

```cpp
// omp_schedule.cpp
// compile with: /openmp
#include <windows.h>
#include <stdio.h>
#include <omp.h>

#define NUM_THREADS 4
#define STATIC_CHUNK 5
#define DYNAMIC_CHUNK 5
#define NUM_LOOPS 20
#define SLEEP_EVERY_N 3

int main( )
{
    int nStatic1[NUM_LOOPS],
        nStaticN[NUM_LOOPS];
    int nDynamic1[NUM_LOOPS],
        nDynamicN[NUM_LOOPS];
    int nGuided[NUM_LOOPS];

    omp_set_num_threads(NUM_THREADS);

    #pragma omp parallel
    {
        #pragma omp for schedule(static, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStatic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(static, STATIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nStaticN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, 1)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamic1[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(dynamic, DYNAMIC_CHUNK)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nDynamicN[i] = omp_get_thread_num( );
        }

        #pragma omp for schedule(guided)
        for (int i = 0 ; i < NUM_LOOPS ; ++i)
        {
            if ((i % SLEEP_EVERY_N) == 0)
                Sleep(0);
            nGuided[i] = omp_get_thread_num( );
        }
    }

    printf_s("------------------------------------------------\n");
    printf_s("| static | static | dynamic | dynamic | guided |\n");
    printf_s("|    1   |    %d   |    1    |    %d    |        |\n",
             STATIC_CHUNK, DYNAMIC_CHUNK);
    printf_s("------------------------------------------------\n");

    for (int i=0; i<NUM_LOOPS; ++i)
    {
        printf_s("|    %d   |    %d   |    %d    |    %d    |"
                 "    %d   |\n",
                 nStatic1[i], nStaticN[i],
                 nDynamic1[i], nDynamicN[i], nGuided[i]);
    }

    printf_s("------------------------------------------------\n");
}
```

```Output
------------------------------------------------
| static | static | dynamic | dynamic | guided |
|    1   |    5   |    1    |    5    |        |
------------------------------------------------
|    0   |    0   |    0    |    2    |    1   |
|    1   |    0   |    3    |    2    |    1   |
|    2   |    0   |    3    |    2    |    1   |
|    3   |    0   |    3    |    2    |    1   |
|    0   |    0   |    2    |    2    |    1   |
|    1   |    1   |    2    |    3    |    3   |
|    2   |    1   |    2    |    3    |    3   |
|    3   |    1   |    0    |    3    |    3   |
|    0   |    1   |    0    |    3    |    3   |
|    1   |    1   |    0    |    3    |    2   |
|    2   |    2   |    1    |    0    |    2   |
|    3   |    2   |    1    |    0    |    2   |
|    0   |    2   |    1    |    0    |    3   |
|    1   |    2   |    2    |    0    |    3   |
|    2   |    2   |    2    |    0    |    0   |
|    3   |    3   |    2    |    1    |    0   |
|    0   |    3   |    3    |    1    |    1   |
|    1   |    3   |    3    |    1    |    1   |
|    2   |    3   |    3    |    1    |    1   |
|    3   |    3   |    0    |    1    |    3   |
------------------------------------------------
```

## <a name="shared"></a><a name="shared-openmp"></a> 共享

指定应在所有线程之间共享一个或多个变量。

```cpp
shared(var)
```

### <a name="parameters"></a>参数

*var*<br/>
要共享的一个或多个变量。 如果指定了多个变量，则用逗号分隔变量名称。

### <a name="remarks"></a>注解

在线程之间共享变量的另一种方法是通过 [copyprivate](#copyprivate) 子句。

`shared` 适用于以下指令：

- [并行](openmp-directives.md#parallel)
- [for](openmp-directives.md#for-openmp)
- [个](openmp-directives.md#sections-openmp)

有关详细信息，请参阅 [2.7.2.4 shared](../2-directives.md#2724-shared)。

### <a name="example"></a>示例

有关使用的示例，请参阅 [私有](#private-openmp) `shared` 。
