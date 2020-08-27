---
title: try-finally 语句
description: 对 __try 和 __finally 结构化异常处理语句的 Microsoft c + + 引用。
ms.date: 08/25/2020
f1_keywords:
- __try
- _try
- __leave_cpp
- __leave
- __finally_cpp
- __try_cpp
- __finally
- _finally
helpviewer_keywords:
- __try keyword [C++]
- __finally keyword [C++]
- __leave keyword [C++]
- try-catch keyword [C++], try-finally keyword
- try-finally keyword [C++]
- __finally keyword [C++], try-finally statement syntax
- __leave keyword [C++], try-finally statement
- structured exception handling [C++], try-finally
ms.assetid: 826e0347-ddfe-4f6e-a7bc-0398e0edc7c2
ms.openlocfilehash: edabbbe35c86f0305e31f36584c4dfe01f2f88cd
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898641"
---
# <a name="try-finally-statement"></a>`try-finally` 语句

`try-finally`语句是**Microsoft 特定**的扩展，支持 C 和 c + + 语言中的结构化异常处理。

## <a name="syntax"></a>语法

以下语法描述了 `try-finally` 语句：

```cpp
    // . . .
    __try {
        // guarded code
    }
    __finally {
        // termination code
    }
    // . . .
```

## <a name="grammar"></a>语法

> *`try-finally-statement`*:\
> &emsp;**`__try`** *`compound-statement`* **`__finally`** *`compound-statement`*

`try-finally`语句是 C 和 c + + 语言的 Microsoft 扩展，使目标应用程序能够在代码块的执行被中断时保证清理代码的执行。 清理包括多个任务，如释放内存、关闭文件和释放文件句柄。 `try-finally` 语句对此类例程特别有用：具有几个位置，在这些位置上执行了检查以找出可能导致例程提前返回内容的错误。

有关相关信息和代码示例，请参阅[ `try-except` 语句](../cpp/try-except-statement.md)。 有关结构化异常处理的一般详细信息，请参阅 [结构化异常处理](../cpp/structured-exception-handling-c-cpp.md)。 若要详细了解如何在 c + +/CLI 托管应用程序中处理异常，请参阅[ `/clr` 下的异常处理](../extensions/exception-handling-cpp-component-extensions.md)。

> [!NOTE]
> 结构化异常处理适用于 Win32 中的 C 和 C++ 源文件。 但是，这不是专门为 C++ 设计的。 您可通过使用 C++ 异常处理来确保提高代码的可移植性。 此外，C++ 异常处理更为灵活，因此它可以处理任何类型的异常。 对于 c + + 程序，建议使用 c + + 异常处理机制)  ([ `try` 、 `catch` 和 `throw` ](../cpp/try-throw-and-catch-statements-cpp.md)语句。

子句后的复合语句 **`__try`** 是受保护的部分。 `__finally` 子句后的复合语句是终止处理程序。 处理程序将指定在退出受保护节时执行的一组操作，无论该操作是通过异常退出受保护的部分 (异常终止) ，还是通过标准终止)  (正常终止。

控制 **`__try`** 通过简单的顺序执行 (贯穿) 来达到一条语句。 当控件进入时 **`__try`** ，其关联的处理程序将变为活动状态。 如果控制流到达 try 块的末尾，执行将继续，如下所示：

1. 调用终止处理程序。

1. 当终止处理程序完成时，在 `__finally` 语句后继续执行。 但是，受保护的部分 (例如，通过 **`goto`** 受保护的主体或 **`return`** 语句) ，在控制流移出受保护部分 *之前* 执行终止处理程序。

   **`__finally`** 语句不会阻止搜索适当的异常处理程序。

如果块中发生异常 **`__try`** ，则操作系统必须查找异常的处理程序，否则程序将失败。 如果找到处理程序，则 **`__finally`** 将执行所有块并在处理程序中恢复执行。

例如，假设一个函数调用系列将函数 A 链接到函数 D，如下图所示。 每个函数均有一个终止处理程序。 如果异常在函数 D 中引发并在函数 A 中得到处理，则当系统展开堆栈时，按以下顺序调用终止处理程序：D、C、B。

![终止&#45;处理程序执行的顺序](../cpp/media/vc38cx1.gif "终止&#45;处理程序执行的顺序") <br/>
终止处理程序执行顺序

> [!NOTE]
> Try-catch 的行为不同于其他一些支持使用 **`finally`** （如 c #）的语言。  单个 **`__try`** 可以有，而不能同时具有 **`__finally`** 和 **`__except`** 。  如果同时使用二者，则外部 try-except 语句必须包含内部 try-finally 语句。  指定何时执行每个块的规则也有所不同。

为了与早期版本兼容，、和 **`_try`** **`_finally`** **`_leave`** 是 **`__try`** 、和的同义词， **`__finally`** **`__leave`** 除非指定了编译器选项[ `/Za` (禁用语言扩展) ](../build/reference/za-ze-disable-language-extensions.md) 。

## <a name="the-__leave-keyword"></a>__leave 关键字

**`__leave`** 关键字仅在语句的受保护部分中有效 `try-finally` ，其作用是跳转到受保护部分的结尾。 执行将在终止处理程序中的第一个语句处继续。

**`goto`** 语句还可以跳出受保护的部分，但会降低性能，因为它会调用堆栈展开。 **`__leave`** 语句更为有效，因为它不会导致堆栈展开。

## <a name="abnormal-termination"></a>异常终止

`try-finally`使用[longjmp](../c-runtime-library/reference/longjmp.md)运行时函数退出语句被视为异常终止。 跳转到语句是非法的 **`__try`** ，但跳出该语句是合法的。 在 **`__finally`** 出发点之间处于活动状态的所有语句 (块) 的正常终止 **`__try`** 和 **`__except`** 处理异常) 的块 (目标，必须运行。 这称为 *本地展开*。

如果某个 **`__try`** 块由于任何原因而提前终止，包括跳出块，则系统会在展开堆栈过程中执行关联的 **`__finally`** 块。 在这种情况下， [`AbnormalTermination`](/windows/win32/Debug/abnormaltermination) **`true`** 如果从块中调用，则函数将返回 **`__finally`** ; 否则返回 **`false`** 。

如果在执行语句的过程中终止进程，则不会调用终止处理程序 `try-finally` 。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编写终止处理程序](../cpp/writing-a-termination-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[关键字](../cpp/keywords-cpp.md)<br/>
[终止处理程序语法](/windows/win32/Debug/termination-handler-syntax)
