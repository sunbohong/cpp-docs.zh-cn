---
description: 了解更多相关信息：使用 Lambda、函数对象和受限函数
title: 使用 Lambda 表达式、函数对象和受限函数
ms.date: 11/04/2016
ms.assetid: 25346cc9-869d-4ada-aad3-e2228cad3d6c
ms.openlocfilehash: bef02f30b5d5b5f11b8051c7a596ac0a141eef0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314446"
---
# <a name="using-lambdas-function-objects-and-restricted-functions"></a>使用 Lambda 表达式、函数对象和受限函数

要在快捷键上运行的 C++ AMP 代码在对 [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) 方法的调用中指定为参数。 可以提供 lambda 表达式或函数对象 (函子) 作为该参数。 此外，lambda 表达式或函数对象可以调用 C++ AMP 限制的函数。 本主题使用数组加法算法演示 lambda、函数对象和受限函数。 下面的示例演示没有 C++ AMP 代码的算法。 已创建长度相等的二维数组。 2 1 相应的整数元素添加并存储在第三个1维数组中。 不使用 C++ AMP。

```cpp
void CpuMethod() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    for (int idx = 0; idx <5; idx++)
    {
        sumCPP[idx] = aCPP[idx] + bCPP[idx];
    }

    for (int idx = 0; idx <5; idx++)
    {
        std::cout <<sumCPP[idx] <<"\n";
    }
}
```

## <a name="lambda-expression"></a>Lambda 表达式

使用 lambda 表达式是使用 C++ AMP 重写代码的最直接的方式。

```cpp
void AddArraysWithLambda() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<const int, 1> a(5, aCPP);

    array_view<const int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp)
        {
             sum[idx] = a[idx] + b[idx];
        });

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

Lambda 表达式必须包含一个索引参数并且必须包括 `restrict(amp)` 。 在此示例中， [array_view](../../parallel/amp/reference/array-view-class.md) `sum` 对象的排名为1。 因此，lambda 语句的参数是一个具有级别1的 [索引](../../parallel/amp/reference/index-class.md) 对象。 在运行时，将对 [array_view](../../parallel/amp/reference/array-view-class.md) 对象中的每个元素执行一次 lambda 表达式。 有关详细信息，请参阅 [Lambda 表达式语法](../../cpp/lambda-expression-syntax.md)。

## <a name="function-object"></a>Function 对象

可以将加速器代码分解为一个函数对象。

```cpp
class AdditionFunctionObject
{
public:
    AdditionFunctionObject(const array_view<int, 1>& a,
    const array_view<int, 1>& b,
    const array_view<int, 1>& sum)
    : a(a), b(b), sum(sum)
    {
    }

    void operator()(index<1> idx) restrict(amp)
    {
        sum[idx] = a[idx] + b[idx];
    }

private:
    array_view<int, 1> a;
    array_view<int, 1> b;
    array_view<int, 1> sum;
};

void AddArraysWithFunctionObject() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<const int, 1> a(5, aCPP);

    array_view<const int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        AdditionFunctionObject(a, b, sum));

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

函数对象必须包含构造函数，并且必须包含函数调用运算符的重载。 函数调用运算符必须包含一个索引参数。 函数对象的实例将作为第二个参数传递到 [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) 方法。 在此示例中，将三个 [array_view](../../parallel/amp/reference/array-view-class.md) 对象传递到函数对象构造函数。 [Array_view](../../parallel/amp/reference/array-view-class.md)对象的 `sum` 排名为1。 因此，函数调用运算符的参数是一个具有秩1的 [索引](../../parallel/amp/reference/index-class.md) 对象。 在运行时，将对 [array_view](../../parallel/amp/reference/array-view-class.md) 对象中的每个元素执行一次此函数。 有关详细信息，请参阅[c + + 标准库中的](../../standard-library/function-objects-in-the-stl.md)[函数调用](../../cpp/function-call-cpp.md)和函数对象。

## <a name="c-amp-restricted-function"></a>C + + AMP-Restricted 函数

您可以通过创建受限函数并从 lambda 表达式或函数对象调用它来进一步因式分解加速器代码。 下面的代码示例演示如何从 lambda 表达式调用受限制的函数。

```cpp
void AddElementsWithRestrictedFunction(index<1> idx, array_view<int, 1> sum, array_view<int, 1> a, array_view<int, 1> b) restrict(amp)
{
    sum[idx] = a[idx] + b[idx];
}

void AddArraysWithFunction() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    array_view<int, 1> a(5, aCPP);

    array_view<int, 1> b(5, bCPP);

    array_view<int, 1> sum(5, sumCPP);

    sum.discard_data();

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp)
        {
            AddElementsWithRestrictedFunction(idx, sum, a, b);
        });

    for (int i = 0; i <5; i++) {
        std::cout <<sum[i] <<"\n";
    }
}
```

受限制的函数必须包括 `restrict(amp)` 并符合 [限制 (C++ AMP) ](../../cpp/restrict-cpp-amp.md)中所述的限制。

## <a name="see-also"></a>请参阅

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Lambda 表达式语法](../../cpp/lambda-expression-syntax.md)<br/>
[函数调用](../../cpp/function-call-cpp.md)<br/>
[C + + 标准库中的函数对象](../../standard-library/function-objects-in-the-stl.md)<br/>
[restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)
