---
title: Structured Exception Handling (C/C++)
description: Microsoft C/c + + 中的结构化异常处理的概述。
ms.date: 08/24/2020
helpviewer_keywords:
- termination handlers [C++], handling exceptions in C++
- structured exception handling [C++]
- try-catch keyword [C++], exception handlers
- C++ exception handling, termination handlers
- try-catch keyword [C++], termination handlers
- C++ exception handling, exception handlers
ms.assetid: dd3b647d-c269-43a8-aab9-ad1458712976
ms.openlocfilehash: 142e89bc82adbe7938e8825029908e814df6055c
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898632"
---
# <a name="structured-exception-handling-cc"></a>Structured Exception Handling (C/C++)

结构化异常处理 (SEH) 是 Microsoft 对 C 的扩展，用于处理特定的异常代码情况（如硬件故障）。 虽然 Windows 和 Microsoft c + + 支持 SEH，但建议使用 ISO 标准 c + + 异常处理。 它使你的代码更具可移植性和灵活性。 但是，若要维护现有代码或特定类型的程序，仍可能必须使用 SEH。

**特定于 Microsoft 的：**

## <a name="grammar"></a>语法

> *`try-except-statement`* :<br/>
> &emsp;**`__try`** *`compound-statement`* **`__except`** **`(`** *`expression`* **`)`** *`compound-statement`*
>
> *`try-finally-statement`* :<br/>
> &emsp;**`__try`** *`compound-statement`* **`__finally`** *`compound-statement`*

## <a name="remarks"></a>注解

通过 SEH，你可以确保在执行意外终止的情况下正确释放资源（如内存块和文件）。 你还可以使用不依赖于 **`goto`** 语句或对返回代码进行详尽测试的简单结构化代码来处理特定问题（例如，内存不足）。

`try-except` `try-finally` 本文中引用的和语句是 C 语言的 Microsoft 扩展。 它们通过使应用程序可以在事件后获得对程序的控制（否则事件将终止执行）来支持 SEH。 尽管 SEH 使用 C++ 源文件，但它并不是专为 C++ 设计的。 如果你在使用[ `/EHa` 或 `/EHsc` ](../build/reference/eh-exception-handling-model.md)选项编译的 c + + 程序中使用 SEH，则会调用本地对象的析构函数，但其他执行行为可能不是你预期的行为。 有关说明，请参阅本文后面的示例。 在大多数情况下，我们建议你使用 Microsoft c + + 编译器还支持的 ISO 标准 [c + + 异常处理](../cpp/try-throw-and-catch-statements-cpp.md)，而不是 SEH。 使用 C++ 异常处理可以确保你的代码更具可移植性，并且你可以处理任何类型的异常。

如果你的 C 代码使用 SEH，则可以将它与使用 c + + 异常处理的 c + + 代码混合使用。 有关信息，请参阅 [在 c + + 中处理结构化异常](../cpp/exception-handling-differences.md)。

有两种 SEH 机制：

- [异常处理程序](../cpp/writing-an-exception-handler.md)或 **`__except`** 块，它们可响应或消除异常。

- 始终调用的[终止处理程序](../cpp/writing-a-termination-handler.md)或 **`__finally`** 块，无论异常是否导致终止。

这两种类型的处理程序是不同的，但通过称为 *展开堆栈的*进程密切相关。 当出现结构化异常时，Windows 将查找最新安装的异常处理程序，该处理程序当前处于活动状态。 该处理程序可以执行以下三个操作之一：

- 无法识别该异常并将控件传递给其他处理程序。

- 识别异常，但将其消除。

- 识别异常，并处理异常。

识别异常的异常处理程序可能不在异常发生时正在运行的函数中。 它可能位于堆栈上更高的函数中。 当前正在运行的函数和堆栈帧上的所有其他函数都将终止。 在此过程中，将 *展开*堆栈。 也就是说，将从堆栈中清除终止函数的本地非静态变量。

当它展开堆栈时，操作系统将调用你为每个函数编写的任何终止处理程序。 通过使用终止处理程序，您可以清理资源，否则由于异常终止而仍将保持打开状态。 如果已输入临界区，可以在终止处理程序中将其退出。 当程序关闭时，可以执行其他内务处理任务，例如关闭和删除临时文件。

## <a name="next-steps"></a>后续步骤

- [编写异常处理程序](../cpp/writing-an-exception-handler.md)

- [编写终止处理程序](../cpp/writing-a-termination-handler.md)

- [处理 C++ 中的结构性异常](../cpp/exception-handling-differences.md)

## <a name="example"></a>示例

如前所述，如果在 c + + 程序中使用 SEH 并使用或选项对其进行编译，则会调用本地对象的析构函数 **`/EHa`** **`/EHsc`** 。 但是，如果您也使用 c + + 异常，则执行过程中的行为可能不是您所期望的。 此示例演示这些行为差异。

```cpp
#include <stdio.h>
#include <Windows.h>
#include <exception>

class TestClass
{
public:
    ~TestClass()
    {
        printf("Destroying TestClass!\r\n");
    }
};

__declspec(noinline) void TestCPPEX()
{
#ifdef CPPEX
    printf("Throwing C++ exception\r\n");
    throw std::exception("");
#else
    printf("Triggering SEH exception\r\n");
    volatile int *pInt = 0x00000000;
    *pInt = 20;
#endif
}

__declspec(noinline) void TestExceptions()
{
    TestClass d;
    TestCPPEX();
}

int main()
{
    __try
    {
        TestExceptions();
    }
    __except(EXCEPTION_EXECUTE_HANDLER)
    {
        printf("Executing SEH __except block\r\n");
    }

    return 0;
}
```

如果使用 **`/EHsc`** 编译此代码，但未定义本地测试控制宏 `CPPEX` ，则 `TestClass` 析构函数将不会运行。 输出如下所示：

```Output
Triggering SEH exception
Executing SEH __except block
```

如果你使用 **`/EHsc`** 来编译代码，并 `CPPEX` 使用 (进行定义， `/DCPPEX` 以便引发 c + + 异常) ，则 `TestClass` 析构函数将运行，输出如下所示：

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

如果你使用 **`/EHa`** 来编译代码，则 `TestClass` 析构函数将通过使用 `std::throw` 或使用 SEH 触发异常来执行是否引发了异常。 也就是说，是否 `CPPEX` 定义了。 输出如下所示：

```Output
Throwing C++ exception
Destroying TestClass!
Executing SEH __except block
```

有关详细信息，请参阅[ `/EH` (异常处理模型) ](../build/reference/eh-exception-handling-model.md)。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[异常处理](../cpp/exception-handling-in-visual-cpp.md)<br/>
[关键字](../cpp/keywords-cpp.md)<br/>
[`<exception>`](../standard-library/exception.md)<br/>
[错误和异常处理](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[结构化异常处理 (Windows) ](/windows/win32/debug/structured-exception-handling)
