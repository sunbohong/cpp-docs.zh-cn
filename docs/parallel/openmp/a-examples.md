---
description: 了解详细信息：。示例
title: A. 示例
ms.date: 01/18/2019
ms.assetid: c0f6192f-a205-449b-b84c-cb30dbcc8b8f
ms.openlocfilehash: d52b59f9f83cf791c03fb49ca726273a2c977e58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342538"
---
# <a name="a-examples"></a>A. 示例

下面是本文档中定义的构造的示例。 指令后面的语句仅在必要时才进行复合，而非复合语句从其前面的指令缩进。

## <a name="a1-a-simple-loop-in-parallel"></a>1. 1 一个并行循环

下面的示例演示如何使用 [parallel for](2-directives.md#251-parallel-for-construct) 指令并行化循环。 默认情况下，循环迭代变量是私有的，因此不需要在私有子句中显式指定它。

```cpp
#pragma omp parallel for
    for (i=1; i<n; i++)
        b[i] = (a[i] + a[i-1]) / 2.0;
```

## <a name="a2-conditional-compilation"></a>2个条件编译

下面的示例演示如何使用 OpenMP 宏 [_OPENMP](2-directives.md#22-conditional-compilation)进行条件编译。 对于 OpenMP 编译， `_OPENMP` 宏会成为定义。

```cpp
# ifdef _OPENMP
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

定义的预处理器运算符允许在一个指令中测试多个宏。

```cpp
# if defined(_OPENMP) && defined(VERBOSE)
    printf_s("Compiled by an OpenMP-compliant implementation.\n");
# endif
```

## <a name="a3-parallel-regions"></a>3个并行区域

[并行](2-directives.md#23-parallel-construct)指令可用于粗粒度的并行程序中。 在下面的示例中，并行区域中的每个线程 `x` 根据线程号决定要处理的全局数组部分：

```cpp
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)
{
    iam = omp_get_thread_num();
    np =  omp_get_num_threads();
    ipoints = npoints / np;
    subdomain(x, iam, ipoints);
}
```

## <a name="a4-the-nowait-clause"></a>4 nowait 子句

如果在并行区域内有多个独立循环，则可以使用 [nowait](2-directives.md#241-for-construct) 子句来避免指令末尾的隐含障碍，如下所示 `for` ：

```cpp
#pragma omp parallel
{
    #pragma omp for nowait
        for (i=1; i<n; i++)
             b[i] = (a[i] + a[i-1]) / 2.0;
    #pragma omp for nowait
        for (i=0; i<m; i++)
            y[i] = sqrt(z[i]);
}
```

## <a name="a5-the-critical-directive"></a>.5 临界指令

下面的示例包含多个 [关键](2-directives.md#262-critical-construct) 指令。 该示例演示了一个排队模型，在该模型中，任务已取消排队并进行处理。 若要防止多个线程取消同一个任务，出列操作必须在部分中 `critical` 。 由于本示例中的两个队列是独立的，因此它们受到 `critical` 不同名称、 *xaxis* 和 *y 轴* 的指令的保护。

```cpp
#pragma omp parallel shared(x, y) private(x_next, y_next)
{
    #pragma omp critical ( xaxis )
        x_next = dequeue(x);
    work(x_next);
    #pragma omp critical ( yaxis )
        y_next = dequeue(y);
    work(y_next);
}
```

## <a name="a6-the-lastprivate-clause"></a>Lastprivate 子句

正确执行有时取决于循环的最后一个迭代赋给变量的值。 此类程序必须将所有此类变量作为参数列出到 [lastprivate](2-directives.md#2723-lastprivate) 子句中，以便变量的值与循环按顺序执行时相同。

```cpp
#pragma omp parallel
{
   #pragma omp for lastprivate(i)
      for (i=0; i<n-1; i++)
         a[i] = b[i] + b[i+1];
}
a[i]=b[i];
```

在前面的示例中， `i` 并行区域末尾的值将等于 `n-1` ，就像在顺序情况下一样。

## <a name="a7-the-reduction-clause"></a>7缩小子句

下面的示例演示了 [缩减](2-directives.md#2726-reduction) 子句：

```cpp
#pragma omp parallel for private(i) shared(x, y, n) \
                         reduction(+: a, b)
    for (i=0; i<n; i++) {
        a = a + x[i];
        b = b + y[i];
    }
```

## <a name="a8-parallel-sections"></a>8个并行节

在下面的示例中， () [部分 2.4.2 sections](2-directives.md#242-sections-construct) ，可以并发执行函数 *xaxis*、 *y 轴* 和 *zaxis* 。 第一个 `section` 指令是可选的。  所有 `section` 指令都需要出现在构造的词法范围内 `parallel sections` 。

```cpp
#pragma omp parallel sections
{
    #pragma omp section
        xaxis();
    #pragma omp section
        yaxis();
    #pragma omp section
        zaxis();
}
```

## <a name="a9-single-directives"></a>单9单指令

下面的示例演示了 [一个](2-directives.md#243-single-construct) 指令。 在此示例中，只有一个线程 (通常是第一个遇到该 `single` 指令的线程) 打印进度消息。 用户不能对将执行该节的线程做出任何假设 `single` 。 所有其他线程将跳过该 `single` 部分，并在构造末尾处的关卡处停止 `single` 。 如果其他线程可以继续而不等待执行节的线程 `single` ，则 `nowait` 可以在指令上指定子句 `single` 。

```cpp
#pragma omp parallel
{
    #pragma omp single
        printf_s("Beginning work1.\n");
    work1();
    #pragma omp single
        printf_s("Finishing work1.\n");
    #pragma omp single nowait
        printf_s("Finished work1 and beginning work2.\n");
    work2();
}
```

## <a name="a10-sequential-ordering"></a>10个顺序排序

[有序部分](2-directives.md#266-ordered-construct) 用于按顺序对从并行完成的工作进行排序。 以下程序按顺序打印索引：

```cpp
#pragma omp for ordered schedule(dynamic)
    for (i=lb; i<ub; i+=st)
        work(i);
void work(int k)
{
    #pragma omp ordered
        printf_s(" %d", k);
}
```

## <a name="a11-a-fixed-number-of-threads"></a>11固定数量的线程

某些程序依赖于固定的预先指定数量的线程来正确执行。  由于线程数的动态调整的默认设置是实现定义的，因此，此类程序可以选择关闭动态线程功能并显式设置线程数以保持可移植性。 下面的示例演示如何使用 [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function)和 [omp_set_num_threads](3-run-time-library-functions.md#311-omp_set_num_threads-function)执行此操作：

```cpp
omp_set_dynamic(0);
omp_set_num_threads(16);
#pragma omp parallel shared(x, npoints) private(iam, ipoints)
{
    if (omp_get_num_threads() != 16)
      abort();
    iam = omp_get_thread_num();
    ipoints = npoints/16;
    do_by_16(x, iam, ipoints);
}
```

在此示例中，仅当程序由16个线程执行时，程序才会正确执行。 如果实现不能支持16线程，则此示例的行为是实现定义的。

无论动态线程设置如何，执行并行区域的线程数在并行区域中保持不变。 动态线程机制确定并行区域开始时使用的线程数，并在区域的持续时间内将其保持不变。

## <a name="a12-the-atomic-directive"></a>答：12的原子指令

下面的示例通过使用 [原子](2-directives.md#264-atomic-construct)指令来避免争用条件 (*x* 的元素同时更新) ：

```cpp
#pragma omp parallel for shared(x, y, index, n)
    for (i=0; i<n; i++)
    {
        #pragma omp atomic
            x[index[i]] += work1(i);
        y[i] += work2(i);
    }
```

`atomic`在此示例中使用指令的优点是，它允许将两个不同的元素更新为并行出现。 如果改为使用 [关键](2-directives.md#262-critical-construct) 指令，则 *x* 的元素的所有更新将按顺序执行，但不按任何保证顺序)  (。

`atomic`指令仅适用于紧随其后的 c 或 c + + 语句。  因此，在本示例中，不会以原子方式更新 *y* 的元素。

## <a name="a13-a-flush-directive-with-a-list"></a>A. 13 带有列表的 flush 指令

下面的示例使用 `flush` 指令对线程对之间的特定对象进行点到点同步：

```cpp
int   sync[NUMBER_OF_THREADS];
float work[NUMBER_OF_THREADS];
#pragma omp parallel private(iam,neighbor) shared(work,sync)
{
    iam = omp_get_thread_num();
    sync[iam] = 0;
    #pragma omp barrier

    // Do computation into my portion of work array
    work[iam] = ...;

    //  Announce that I am done with my work
    // The first flush ensures that my work is
    // made visible before sync.
    // The second flush ensures that sync is made visible.
    #pragma omp flush(work)
    sync[iam] = 1;
    #pragma omp flush(sync)

    // Wait for neighbor
    neighbor = (iam>0 ? iam : omp_get_num_threads()) - 1;
    while (sync[neighbor]==0)
    {
        #pragma omp flush(sync)
    }

    // Read neighbor's values of work array
    ... = work[neighbor];
}
```

## <a name="a14-a-flush-directive-without-a-list"></a>如果没有列表，则为 14 A flush 指令

下面的示例 ([节 2.6.5](2-directives.md#265-flush-directive)) 将受指令影响的共享对象 `flush` 与不受影响的共享对象中没有列表区分开来：

```cpp
// omp_flush_without_list.c
#include <omp.h>

int x, *p = &x;

void f1(int *q)
{
    *q = 1;
    #pragma omp flush
    // x, p, and *q are flushed
    //   because they are shared and accessible
    // q is not flushed because it is not shared.
}

void f2(int *q)
{
    #pragma omp barrier
    *q = 2;

    #pragma omp barrier
    // a barrier implies a flush
    // x, p, and *q are flushed
    //   because they are shared and accessible
    // q is not flushed because it is not shared.
}

int g(int n)
{
    int i = 1, j, sum = 0;
    *p = 1;

    #pragma omp parallel reduction(+: sum) num_threads(10)
    {
        f1(&j);
        // i, n and sum were not flushed
        //   because they were not accessible in f1
        // j was flushed because it was accessible
        sum += j;
        f2(&j);
        // i, n, and sum were not flushed
        //   because they were not accessible in f2
        // j was flushed because it was accessible
        sum += i + j + *p + n;
    }
    return sum;
}

int main()
{
}
```

## <a name="a15-the-number-of-threads-used"></a>15-使用的线程数

对于 [3.1.2) 部分](3-run-time-library-functions.md#312-omp_get_num_threads-function) ，请考虑以下不正确的示例 (：

```cpp
np = omp_get_num_threads(); // misplaced
#pragma omp parallel for schedule(static)
    for (i=0; i<np; i++)
        work(i);
```

`omp_get_num_threads()`调用在代码的串行部分返回1，因此在前面的示例中， *np* 将始终等于1。 若要确定将为并行区域部署的线程数，调用应位于并行区域内。

下面的示例演示如何重写此程序，而不包括对线程数的查询：

```cpp
#pragma omp parallel private(i)
{
    i = omp_get_thread_num();
    work(i);
}
```

## <a name="a16-locks"></a>十六个锁

在下面的示例中， (为 [3.2) 节](3-run-time-library-functions.md#32-lock-functions) ，则锁函数的参数应具有类型 `omp_lock_t` ，并且无需刷新。  锁函数会导致线程在等待进入第一个关键部分时处于空闲状态，但要在等待进入第二部分时执行其他工作。  `omp_set_lock`函数会阻止，但 `omp_test_lock` 函数不会，这样就可以完成中的工作 `skip()` 。

```cpp
// omp_using_locks.c
// compile with: /openmp /c
#include <stdio.h>
#include <omp.h>

void work(int);
void skip(int);

int main() {
   omp_lock_t lck;
   int id;

   omp_init_lock(&lck);
   #pragma omp parallel shared(lck) private(id)
   {
      id = omp_get_thread_num();

      omp_set_lock(&lck);
      printf_s("My thread id is %d.\n", id);

      // only one thread at a time can execute this printf
      omp_unset_lock(&lck);

      while (! omp_test_lock(&lck)) {
         skip(id);   // we do not yet have the lock,
                     // so we must do something else
      }
      work(id);     // we now have the lock
                    // and can do the work
      omp_unset_lock(&lck);
   }
   omp_destroy_lock(&lck);
}
```

## <a name="a17-nestable-locks"></a>17 A.17 锁

下面的示例 ([第3.2 节](3-run-time-library-functions.md#32-lock-functions)) 演示了如何使用 a.17 锁将更新同时同步到整个结构和其成员之一。

```cpp
#include <omp.h>
typedef struct {int a,b; omp_nest_lock_t lck;} pair;

void incr_a(pair *p, int a)
{
    // Called only from incr_pair, no need to lock.
    p->a += a;
}

void incr_b(pair *p, int b)
{
    // Called both from incr_pair and elsewhere,
    // so need a nestable lock.

    omp_set_nest_lock(&p->lck);
    p->b += b;
    omp_unset_nest_lock(&p->lck);
}

void incr_pair(pair *p, int a, int b)
{
    omp_set_nest_lock(&p->lck);
    incr_a(p, a);
    incr_b(p, b);
    omp_unset_nest_lock(&p->lck);
}

void f(pair *p)
{
    extern int work1(), work2(), work3();
    #pragma omp parallel sections
    {
        #pragma omp section
            incr_pair(p, work1(), work2());
        #pragma omp section
            incr_b(p, work3());
    }
}
```

## <a name="a18-nested-for-directives"></a>用于指令的18个嵌套

下面的 `for` [指令嵌套](2-directives.md#29-directive-nesting) 示例是相容的，因为内部和外部 `for` 指令绑定到不同的并行区域：

```cpp
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
        {
            #pragma omp parallel shared(i, n)
            {
                #pragma omp for
                    for (j=0; j<n; j++)
                        work(i, j);
            }
        }
}
```

前面示例的以下变体也符合：

```cpp
#pragma omp parallel default(shared)
{
    #pragma omp for
        for (i=0; i<n; i++)
            work1(i, n);
}

void work1(int i, int n)
{
    int j;
    #pragma omp parallel default(shared)
    {
        #pragma omp for
            for (j=0; j<n; j++)
                work2(i, j);
    }
    return;
}
```

## <a name="a19-examples-showing-incorrect-nesting-of-work-sharing-directives"></a>19示例显示错误的工作共享指令嵌套

本节中的示例说明 [嵌套](2-directives.md#29-directive-nesting) 规则。

下面的示例是不相容的，因为内部和外部 `for` 指令被嵌套并绑定到同一个 `parallel` 指令：

```cpp
void wrong1(int n)
{
  #pragma omp parallel default(shared)
  {
      int i, j;
      #pragma omp for
      for (i=0; i<n; i++) {
          #pragma omp for
              for (j=0; j<n; j++)
                 work(i, j);
     }
   }
}
```

下面的示例的以下动态嵌套版本也不相容：

```cpp
void wrong2(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++)
        work1(i, n);
  }
}

void work1(int i, int n)
{
  int j;
  #pragma omp for
    for (j=0; j<n; j++)
      work2(i, j);
}
```

下面的示例是不相容的 `for` ，因为和 `single` 指令是嵌套的，并且它们绑定到同一个并行区域：

```cpp
void wrong3(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        #pragma omp single
          work(i);
      }
  }
}
```

下面的示例是不相容的，因为 `barrier` 中的指令 `for` 可能会导致死锁：

```cpp
void wrong4(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        work1(i);
        #pragma omp barrier
        work2(i);
      }
  }
}
```

下面的示例是不相容的，因为 `barrier` 由于一次只有一个线程可以进入临界区，导致死锁的结果：

```cpp
void wrong5()
{
  #pragma omp parallel
  {
    #pragma omp critical
    {
       work1();
       #pragma omp barrier
       work2();
    }
  }
}
```

下面的示例是不相容的，因为 `barrier` 由于只有一个线程执行部分，导致死锁的结果是 `single` ：

```cpp
void wrong6()
{
  #pragma omp parallel
  {
    setup();
    #pragma omp single
    {
      work1();
      #pragma omp barrier
      work2();
    }
    finish();
  }
}
```

## <a name="a20-bind-barrier-directives"></a>20个绑定屏障指令

指令绑定规则为 `barrier` 绑定到最近的封闭指令的指令调用 `parallel` 。 有关指令绑定的详细信息，请参阅 [2.8 节](2-directives.md#28-directive-binding)。

在下面的示例中，从 *main* 到 *sub2* 的调用是相容的，因为 `barrier` *sub3* 中的 () 绑定到 *sub2* 中的并行区域。 从 *main* 到 *sub1* 的调用是相容的，因为 `barrier` 绑定到子例程 *sub2* 中的并行区域。  从 *main* 到 *sub3* 的调用是相容的，因为未 `barrier` 绑定到任何并行区域，并且将被忽略。 此外， `barrier` 仅同步封闭并行区域中的线程组，而不同步在 *sub1* 中创建的所有线程。

```cpp
int main()
{
    sub1(2);
    sub2(2);
    sub3(2);
}

void sub1(int n)
{
    int i;
    #pragma omp parallel private(i) shared(n)
    {
        #pragma omp for
        for (i=0; i<n; i++)
            sub2(i);
    }
}

void sub2(int k)
{
     #pragma omp parallel shared(k)
     sub3(k);
}

void sub3(int n)
{
    work(n);
    #pragma omp barrier
    work(n);
}
```

## <a name="a21-scope-variables-with-the-private-clause"></a>带有 private 子句的21个作用域变量

`i`以下示例中的和的值在 `j` 从并行区域退出时未定义：

```cpp
int i, j;
i = 1;
j = 2;
#pragma omp parallel private(i) firstprivate(j)
{
  i = 3;
  j = j + 2;
}
printf_s("%d %d\n", i, j);
```

有关子句的详细信息 `private` ，请参阅 [2.7.2.1 部分](2-directives.md#2721-private)。

## <a name="a22-the-defaultnone-clause"></a>答 (none) 子句的默认值

下面的示例将子句影响的变量与不是的变量区分开来 `default(none)` ：

```cpp
// openmp_using_clausedefault.c
// compile with: /openmp
#include <stdio.h>
#include <omp.h>

int x, y, z[1000];
#pragma omp threadprivate(x)

void fun(int a) {
   const int c = 1;
   int i = 0;

   #pragma omp parallel default(none) private(a) shared(z)
   {
      int j = omp_get_num_thread();
             //O.K.  - j is declared within parallel region
      a = z[j];       // O.K.  - a is listed in private clause
                      //      - z is listed in shared clause
      x = c;          // O.K.  - x is threadprivate
                      //      - c has const-qualified type
      z[i] = y;       // C3052 error - cannot reference i or y here

      #pragma omp for firstprivate(y)
         for (i=0; i<10 ; i++) {
            z[i] = y;  // O.K. - i is the loop control variable
                       // - y is listed in firstprivate clause
          }
       z[i] = y;   // Error - cannot reference i or y here
   }
}
```

有关子句的详细信息 `default` ，请参阅 [2.7.2.5 部分](2-directives.md#2725-default)。

## <a name="a23-examples-of-the-ordered-directive"></a>有序指令的23示例

具有使用子句指定的多个有序节可能 `for` `ordered` 。 第一个示例是不相容的，因为 API 指定了以下规则：

"具有构造的循环迭代不得多次 `for` 执行同一 `ordered` 指令，并且它不能执行多个 `ordered` 指令。"  (参阅 [2.6.6 部分](2-directives.md#266-ordered-construct)。 ) 

在此不相容的示例中，所有迭代执行两个有序部分：

```cpp
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    #pragma omp ordered
    { ... }
    ...
    #pragma omp ordered
    { ... }
    ...
}
```

以下符合的示例显示了一个 `for` 具有多个有序节的：

```cpp
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    if (i <= 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
    (i > 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
}
```

## <a name="a24-example-of-the-private-clause"></a>私有子句的24示例

并行区域的 [私有](2-directives.md#2721-private) 子句仅对区域的词法范围有效，而不适用于区域的动态区。  因此，在下面的示例中，例程 f 中循环内循环 *的任何* 使用都 `for` 是指的私有副本，而例程 *g* 中的用法指的是全局 *a*。 

```cpp
int a;

void f(int n)
{
    a = 0;

    #pragma omp parallel for private(a)
    for (int i=1; i<n; i++)
    {
        a = i;
        g(i, n);
        d(a);     // Private copy of "a"
        ...
    }
    ...

void g(int k, int n)
{
    h(k,a); // The global "a", not the private "a" in f
}
```

## <a name="a25-examples-of-the-copyprivate-data-attribute-clause"></a>Copyprivate 数据 attribute 子句的25个示例

**示例1：**[Copyprivate](2-directives.md#2728-copyprivate)子句可用于将单个线程获取的值直接广播到其他线程中的私有变量的所有实例。

```cpp
float x, y;
#pragma omp threadprivate(x, y)

void init( )
{
    float a;
    float b;

    #pragma omp single copyprivate(a,b,x,y)
    {
        get_values(a,b,x,y);
    }

    use_values(a, b, x, y);
}
```

如果从串行区域调用例程 *初始化* ，则其行为不会受到指令的存在的影响。 在一个线程执行了对 *get_values* 例程的调用之后，任何线程都不会离开构造，直到所有线程中 *a*、 *b*、 *x* 和 *y* 指定的私有对象均已使用读取的值进行定义。

**示例2：** 与前面的示例不同，假设读取必须由特定的线程执行，比如主线程。 在这种情况下， `copyprivate` 子句不能用于直接执行广播，但它可用于提供对临时共享对象的访问权限。

```cpp
float read_next( )
{
    float * tmp;
    float return_val;

    #pragma omp single copyprivate(tmp)
    {
        tmp = (float *) malloc(sizeof(float));
    }

    #pragma omp master
    {
        get_float( tmp );
    }

    #pragma omp barrier
    return_val = *tmp;
    #pragma omp barrier

    #pragma omp single
    {
       free(tmp);
    }

    return return_val;
}
```

**示例3：** 假设并行区域中所需的锁定对象数在输入之前不能很容易确定。 `copyprivate`子句可用于提供对在该并行区域中分配的共享锁定对象的访问权限。

```cpp
#include <omp.h>

omp_lock_t *new_lock()
{
    omp_lock_t *lock_ptr;

    #pragma omp single copyprivate(lock_ptr)
    {
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));
        omp_init_lock( lock_ptr );
    }

    return lock_ptr;
}
```

## <a name="a26-the-threadprivate-directive"></a>Threadprivate 指令

下面的示例演示如何使用 [threadprivate](2-directives.md#271-threadprivate-directive) 指令为每个线程分配一个单独的计数器。

### <a name="example-1"></a>示例 1

```cpp
int counter = 0;
#pragma omp threadprivate(counter)

int sub()
{
    counter++;
    return(counter);
}
```

### <a name="example-2"></a>示例 2

```cpp
int sub()
{
    static int counter = 0;
    #pragma omp threadprivate(counter)
    counter++;
    return(counter);
}
```

## <a name="a27-c99-variable-length-arrays"></a>. 27 C99 可变长度数组

下面的示例演示如何在 [firstprivate](2-directives.md#2722-firstprivate) 指令中 (VLAs) 使用 C99 可变长度数组。

> [!NOTE]
> Visual C++ 当前不支持可变长度数组。

```cpp
void f(int m, int C[m][m])
{
    double v1[m];
    ...
    #pragma omp parallel firstprivate(C, v1)
    ...
}
```

## <a name="a28-the-num_threads-clause"></a>A. 28 num_threads 子句

下面的示例演示 [num_threads](2-directives.md#23-parallel-construct) 子句。 并行区域的执行最多为10个线程。

```cpp
#include <omp.h>
main()
{
    omp_set_dynamic(1);
    ...
    #pragma omp parallel num_threads(10)
    {
        ... parallel region ...
    }
}
```

## <a name="a29-work-sharing-constructs-inside-a-critical-construct"></a>严重构造中的29个工作共享构造

下面的示例演示如何在构造内使用工作共享构造 `critical` 。 此示例是相容的，因为工作共享构造和 `critical` 构造不绑定到同一个并行区域。

```cpp
void f()
{
  int i = 1;
  #pragma omp parallel sections
  {
    #pragma omp section
    {
      #pragma omp critical (name)
      {
        #pragma omp parallel
        {
          #pragma omp single
          {
            i++;
          }
        }
      }
    }
  }
}
```

## <a name="a30-reprivatization"></a>A.30 重新私有化30

下面的示例演示了变量的 a.30 重新私有化。 可以 `private` 在嵌套指令中再次标记私有变量。 不需要在封闭并行区域中共享这些变量。

```cpp
int i, a;
...
#pragma omp parallel private(a)
{
  ...
  #pragma omp parallel for private(a)
  for (i=0; i<10; i++)
     {
       ...
     }
}
```

## <a name="a31-thread-safe-lock-functions"></a>31个线程安全的锁函数

下面的 c + + 示例演示如何使用 [omp_init_lock](3-run-time-library-functions.md#321-omp_init_lock-and-omp_init_nest_lock-functions)初始化并行区域中的锁的数组。

```cpp
// A_13_omp_init_lock.cpp
// compile with: /openmp
#include <omp.h>

omp_lock_t *new_locks() {
   int i;
   omp_lock_t *lock = new omp_lock_t[1000];
   #pragma omp parallel for private(i)
   for (i = 0 ; i < 1000 ; i++)
      omp_init_lock(&lock[i]);

   return lock;
}

int main () {}
```
