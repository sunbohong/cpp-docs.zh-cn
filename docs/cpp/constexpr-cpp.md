---
title: constexpr (C++)
description: C + + 语言 constexpr 关键字指南。
ms.date: 01/28/2020
f1_keywords:
- constexpr_cpp
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
no-loc:
- constexpr
- const
- inline
- goto
- try
- if
- switch
- for
- while
ms.openlocfilehash: 57ebf4bf69c768bfcd2e4d26a5c3334ca788b08f
ms.sourcegitcommit: a6b97f5d78299ad93675de2fe0f0561f528d26c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "90569561"
---
# <a name="no-locconstexpr-c"></a>constexpr (C++)

关键字 **`constexpr`** 是在 c + + 11 中引入的，并在 c + + 14 中得到改进。 它表示* const ant 表达式*。 与类似 **`const`** ，可将其应用于变量：当任何代码尝试将值进行 mod 时，将引发编译器错误 if 。 与不同 **`const`** ， **`constexpr`** 还可以应用于函数和类 const ructors。 **`constexpr`** 指示值或返回值为 ant，并在 const 编译时计算（如果可能）。

**`constexpr`** 整数值可用于需要整数的任何位置 const ，例如模板参数和数组声明中的。 在编译时（而非运行时）计算某个值时，它可帮助您的程序运行速度更快，使用更少的内存。

为了限制编译时 ant 计算的复杂性 const ，以及它们对编译时间的潜在影响，c + + 14 标准要求 ant 表达式中的类型为 const [文本类型](trivial-standard-layout-and-pod-types.md#literal_types)。

## <a name="syntax"></a>语法

> **`constexpr`***文本类型* *ident if ier* **=** * const * **;**\
> **`constexpr`***文本类型* *ident if ier* **{** * const ant-expression* **}** **;**\
> **`constexpr`***文本类型* *ident if ier* ** (** *参数* **) ** **;**\
> **`constexpr`***ctor* ** (** *参数* **) ** **;**

## <a name="parameters"></a>参数

*化*\
一个或多个参数，每个参数必须是文本类型，并且本身必须是 const ant 表达式。

## <a name="return-value"></a>返回值

**`constexpr`** 变量或函数必须返回[文本类型](trivial-standard-layout-and-pod-types.md#literal_types)。

## <a name="no-locconstexpr-variables"></a>constexpr 变量

和变量的主要 d if f) **`const`** **`constexpr`** 是在 **`const`** 运行时，可以将变量的初始化推迟。 **`constexpr`** 变量必须在编译时进行初始化。  所有 **`constexpr`** 变量都是 **`const`** 。

- **`constexpr`** 如果变量具有文本类型并已初始化，则可以使用声明该变量。 如果初始化 for 由 ructor 按 med-v 进行 const ，则 const 必须将 ructor 声明为 **`constexpr`** 。

- **`constexpr`** 当同时满足这两个条件时，可以声明引用：引用的对象由 const ant 表达式进行初始化，并且在初始化期间调用的任何隐式转换也是 const ant 表达式。

- 变量或函数的所有声明都 **`constexpr`** 必须具有 **`constexpr`** 规范 if ier。

```cpp
constexpr float x = 42.0;
constexpr float y{108};
constexpr float z = exp(5, 3);
constexpr int i; // Error! Not initialized
int j = 0;
constexpr int k = j + 1; //Error! j not a constant expression
```

## <a name="no-locconstexpr-functions"></a><a name="constexpr_functions"></a> constexpr 函数

**`constexpr`** 当使用代码需要函数时，该函数的返回值可在编译时。 使用代码要求在编译时返回值以初始化 **`constexpr`** 变量，或提供一个非类型模板参数。 如果其参数为 **`constexpr`** 值， **`constexpr`** 函数将生成编译时 const ant。 使用非参数调用时 **`constexpr`** ，或在编译时不需要其值时，它会在运行时生成一个值，如常规函数。  (这种双重行为使您不必编写 **`constexpr`** 同一函数的和非 **`constexpr`** 版本。 ) 

**`constexpr`** 函数或 const ructor 是隐式的 **`inline`** 。

以下规则适用于 constexpr 函数：

- **`constexpr`** 函数必须接受并仅返回[文本类型](trivial-standard-layout-and-pod-types.md#literal_types)。

- **`constexpr`** 函数可以是递归的。

- 它不能是 [虚拟](../cpp/virtual-cpp.md)的。 const不能定义 ructor，因为 **`constexpr`** 封闭类具有任何虚拟基类。

- 主体可以定义为 `= default` 或 `= delete`。

- 主体不能包含任何 **`goto`** 语句或 **`try`** 块。

- 非模板的显式专用化 **`constexpr`** 可以声明为 **`constexpr`** ：

- 模板的显式专用化 **`constexpr`** 还不一定要 **`constexpr`** ：

以下规则适用于 **`constexpr`** Visual Studio 2017 和更高版本中的函数：

- 它可以包含 **`if`** 和 **`switch`** 语句以及所有循环语句，包括 **`for`** 、基于范围的 **`for`** 、 **`while`** 和。 ** while **

- 它可能包含局部变量声明，但必须对变量进行初始化。 它必须是文本类型，不能是 **`static`** 或线程本地类型。 本地声明的变量不需要为 **`const`** ，并且可能会改变。

- **`constexpr`** 非 **`static`** 成员函数不需要是隐式的 **`const`** 。

```cpp
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
}
```

> [!TIP]
> 在 Visual Studio 调试器中，调试未优化的调试版本时，可以 **`constexpr`** 通过在函数内放置一个断点来确定是否在编译时计算该函数。 如果命中该断点，则在运行时调用该函数。  如果未命中，则在编译时调用该函数。

## <a name="extern-no-locconstexpr"></a>部 constexpr

[/Zc： externConstexpr](../build/reference/zc-externconstexpr.md)编译器选项导致编译器将[外部链接](../c-language/external-linkage.md)应用到使用**extern constexpr **声明的变量。 在 Visual Studio 的早期版本中，默认情况下或在 **/zc： externConstexpr-** 为 spec if i 时， **`constexpr`** 即使使用关键字，visual studio 也会对变量应用内部链接 **`extern`** 。 **/Zc： externConstexpr**选项从 Visual Studio 2017 Update 15.6 开始提供，并在默认情况下处于关闭状态。 [/Permissive-](../build/reference/permissive-standards-conformance.md)选项不启用 **/zc： externConstexpr**。

## <a name="example"></a>示例

下面的示例演示 **`constexpr`** 变量、函数和用户定义类型。 在中的最后一个语句中 `main()` ， **`constexpr`** 成员函数 `GetValue()` 是一个运行时调用，因为在编译时不需要知道值。

```cpp
// constexpr.cpp
// Compile with: cl /EHsc /W4 constexpr.cpp
#include <iostream>

using namespace std;

// Pass by value
constexpr float exp(float x, int n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp(x * x, n / 2) :
        exp(x * x, (n - 1) / 2) * x;
}

// Pass by reference
constexpr float exp2(const float& x, const int& n)
{
    return n == 0 ? 1 :
        n % 2 == 0 ? exp2(x * x, n / 2) :
        exp2(x * x, (n - 1) / 2) * x;
}

// Compile-time computation of array length
template<typename T, int N>
constexpr int length(const T(&)[N])
{
    return N;
}

// Recursive constexpr function
constexpr int fac(int n)
{
    return n == 1 ? 1 : n * fac(n - 1);
}

// User-defined type
class Foo
{
public:
    constexpr explicit Foo(int i) : _i(i) {}
    constexpr int GetValue() const
    {
        return _i;
    }
private:
    int _i;
};

int main()
{
    // foo is const:
    constexpr Foo foo(5);
    // foo = Foo(6); //Error!

    // Compile time:
    constexpr float x = exp(5, 3);
    constexpr float y { exp(2, 5) };
    constexpr int val = foo.GetValue();
    constexpr int f5 = fac(5);
    const int nums[] { 1, 2, 3, 4 };
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };

    // Run time:
    cout << "The value of foo is " << foo.GetValue() << endl;
}
```

## <a name="requirements"></a>要求

Visual Studio 2015 或更高版本。

## <a name="see-also"></a>请参阅

[声明和定义](../cpp/declarations-and-definitions-cpp.md)\
[const](../cpp/const-cpp.md)
