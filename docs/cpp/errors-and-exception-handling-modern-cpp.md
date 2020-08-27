---
title: 异常和错误处理的新式 c + + 最佳做法
description: 现代 c + + 如何支持针对错误代码的异常编程样式。
ms.date: 08/24/2020
ms.topic: conceptual
ms.assetid: a6c111d0-24f9-4bbb-997d-3db4569761b7
ms.openlocfilehash: b402c93ea5af3cc7dab418b6dea58446ae300c67
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898370"
---
# <a name="modern-c-best-practices-for-exceptions-and-error-handling"></a>异常和错误处理的新式 c + + 最佳做法

在现代 c + + 中，在大多数情况下，报告和处理逻辑错误和运行时错误的首选方法是使用异常。 当堆栈中可能包含检测到错误的函数之间的多个函数调用，以及具有用于处理错误的上下文的函数时，尤其如此。 异常为检测到错误的代码提供了一种明确定义的方法，以便在调用堆栈上传递信息。

## <a name="use-exceptions-for-exceptional-code"></a>异常代码使用异常

程序错误通常分为两类：由编程错误引起的逻辑错误，例如，"索引超出范围" 错误。 并且是超出程序员控件的运行时错误，例如，"网络服务不可用" 错误。 在 C 样式编程和 COM 中，通过返回一个表示错误代码或特定函数的状态代码的值，或者通过设置调用方在每次调用函数后可以选择检索的全局变量来查看是否报告了错误，从而管理错误报告。 例如，COM 编程使用 HRESULT 返回值将错误传递给调用方。 和 Win32 API 包含 `GetLastError` 用于检索调用堆栈报告的最后一个错误的函数。 在这两种情况下，由调用方来识别代码并对其进行适当的响应。 如果调用方未显式处理错误代码，则程序可能会崩溃，而不发出警告。 或者，它可能会使用错误的数据继续执行，并生成不正确的结果。

在现代 c + + 中首选例外，原因如下：

- 异常会强制调用代码识别错误情况并对其进行处理。 未经处理的异常停止程序执行。

- 异常跳转到调用堆栈中可处理错误的点。 中间函数可以让异常传播。 它们不必与其他层进行协调。

- 异常堆栈展开机制会在引发异常后根据定义完善的规则破坏范围内的所有对象。

- 异常使检测到错误的代码和处理错误的代码之间的完全分离。

以下简化的示例显示了在 c + + 中引发和捕获异常的必要语法。

```cpp
#include <stdexcept>
#include <limits>
#include <iostream>

using namespace std;

void MyFunc(int c)
{
    if (c > numeric_limits< char> ::max())
        throw invalid_argument("MyFunc argument too large.");
    //...
}

int main()
{
    try
    {
        MyFunc(256); //cause an exception to throw
    }

    catch (invalid_argument& e)
    {
        cerr << e.what() << endl;
        return -1;
    }
    //...
    return 0;
}
```

C + + 中的异常类似于 c # 和 Java 等语言。 在 **`try`** 块中，如果*引发*异常，则它将被*caught* **`catch`** 其类型与异常匹配的第一个关联块捕获。 换言之，执行从语句跳转 **`throw`** 到 **`catch`** 语句。 如果未找到可用的 catch 块， `std::terminate` 则将调用并退出程序。 在 c + + 中，可能会引发任何类型;但是，我们建议你引发直接或间接从派生的类型 `std::exception` 。 在上面的示例中，异常类型在 [`invalid_argument`](../standard-library/invalid-argument-class.md) 标头文件的标准库中定义 [`<stdexcept>`](../standard-library/stdexcept.md) 。 C + + 不提供或不需要 **`finally`** 块，以确保在引发异常时释放所有资源。 资源获取是 (RAII) 使用智能指针的使用情况进行初始化，它为资源清理提供所需的功能。 有关详细信息，请参阅 [如何：设计异常安全性](how-to-design-for-exception-safety.md)。 有关 c + + 堆栈展开机制的信息，请参阅 [异常和堆栈展开](exceptions-and-stack-unwinding-in-cpp.md)。

## <a name="basic-guidelines"></a>基本指导原则

强大的错误处理对于任何编程语言都很有挑战性。 尽管异常提供了多个支持良好错误处理的功能，但它们无法为你完成所有工作。 若要实现异常机制的优点，请在设计代码时记住异常。

- 使用断言来检查绝不应发生的错误。 使用异常来检查可能出现的错误，例如，公共函数参数的输入验证中的错误。 有关详细信息，请参阅 [异常与断言](#exceptions_versus_assertions) 部分。

- 当处理错误的代码与通过一个或多个干预函数调用检测到错误的代码分离时，使用异常。 当处理错误的代码与检测到错误的代码紧密耦合时，考虑是否使用错误代码而不是在性能关键循环中。

- 对于可能引发或传播异常的每个函数，请提供以下三种异常保证之一：强保障、基本保证或 nothrow (noexcept) 保证。 有关详细信息，请参阅 [如何：设计异常安全性](how-to-design-for-exception-safety.md)。

- 按值引发异常，按引用来捕获异常。 不要捕获无法处理的内容。

- 不要使用 c + + 11 中已弃用的异常规范。 有关详细信息，请参阅[异常规范和 `noexcept` ](#exception_specifications_and_noexcept)部分。

- 应用时使用标准库异常类型。 从[ `exception` 类](../standard-library/exception-class.md)层次结构派生自定义异常类型。

- 不允许对析构函数或内存释放函数进行转义。

## <a name="exceptions-and-performance"></a>异常和性能

如果没有引发异常，则异常机制的性能开销将最小。 如果引发了异常，堆栈遍历和展开的开销大致相当于函数调用的成本。 在输入块后，需要其他数据结构来跟踪调用堆栈 **`try`** ，并在引发异常时展开堆栈需要其他说明。 但在大多数情况下，性能和内存占用量的成本并不重要。 异常对性能的不利影响可能仅对内存约束的系统很重要。 或者，在性能关键循环中，错误可能会定期发生，并且代码与处理它的代码之间的紧密耦合。 在任何情况下，不可能知道异常的实际成本，而不会进行分析和度量。 即使在这种极少的情况下，成本很高，你也可以将其与更好的正确性、更易于维护性以及由设计良好的异常策略提供的其他优势进行权衡。

## <a name="exceptions-versus-assertions"></a><a name="exceptions_versus_assertions"></a> 异常与断言

异常和断言是在程序中检测运行时错误的两种不同机制。 在 `assert` 开发过程中使用语句来测试条件，前提是所有代码都是正确的。 由于错误表明必须修复代码中的某些内容，因此不需要使用异常来处理此类错误。 它不表示程序必须在运行时恢复的条件。 `assert`在语句处停止执行，以便您可以检查调试器中的程序状态。 异常继续从第一个适当的 catch 处理程序执行。 使用异常检查在运行时可能发生的错误条件，即使代码正确，例如，"找不到文件" 或 "内存不足"。 异常可以处理这些情况，即使恢复只是将消息输出到日志并结束程序。 始终使用异常检查公共函数的自变量。 即使您的函数没有错误，也可能无法完全控制用户可能传递给它的参数。

## <a name="c-exceptions-versus-windows-seh-exceptions"></a>C + + 异常与 Windows SEH 异常

C 和 c + + 程序可以在 Windows 操作系统中使用结构化异常处理 (SEH) 机制。 SEH 中的概念与 c + + 异常中的概念相似，不同之处在于 SEH 使用 **`__try`** 、 **`__except`** 和 **`__finally`** 构造而不是 **`try`** 和 **`catch`** 。 在 Microsoft c + + 编译器 (MSVC) 中，为 SEH 实现 c + + 异常。 但是，在编写 c + + 代码时，请使用 c + + 异常语法。

有关 SEH 的详细信息，请参阅 [结构化异常处理 (C/c + +) ](structured-exception-handling-c-cpp.md)。

## <a name="exception-specifications-and-noexcept"></a><a name="exception_specifications_and_noexcept"></a> 异常规范和 `noexcept`

异常规范是在 c + + 中引入的，它是一种指定函数可能引发的异常的方法。 不过，异常规范在实践中已证明有问题，并且已在 c + + 11 草案标准中弃用。 建议你不要使用 **`throw`** 除外的异常规范 `throw()` ，这表示函数不允许对任何异常进行转义。 如果你必须使用已弃用窗体的异常规范 `throw( type-name )` ，则 MSVC 支持是有限的。 有关详细信息，请参阅 [异常规范 (throw) ](exception-specifications-throw-cpp.md)。 **`noexcept`** 说明符在 c + + 11 中引入为的首选替代项 `throw()` 。

## <a name="see-also"></a>请参阅

[如何：异常和非异常代码之间的接口](../cpp/how-to-interface-between-exceptional-and-non-exceptional-code.md)<br/>
[C + + 语言参考](../cpp/cpp-language-reference.md)<br/>
[C + + 标准库](../standard-library/cpp-standard-library-reference.md)
