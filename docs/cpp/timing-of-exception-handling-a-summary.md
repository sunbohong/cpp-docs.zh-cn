---
title: 异常处理的计时：摘要
description: 在 Microsoft c + + 中执行异常处理的时间和顺序。
ms.date: 08/24/2020
helpviewer_keywords:
- sequence [C++]
- sequence, of handlers
- exception handling [C++], timing
- setjmpex.h
- termination handlers [C++], timing
- setjmp.h
- handlers [C++], order of exception
- structured exception handling [C++], timing
ms.assetid: 5d1da546-73fd-4673-aa1a-7ac0f776c420
ms.openlocfilehash: 2ce501d8d74b6f0f7ca92e193c39f8ce58a66053
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898362"
---
# <a name="timing-of-exception-handling-a-summary"></a>异常处理的计时：摘要

无论语句块的终止方式如何，都将执行终止处理程序 **`__try`** 。 导致的原因包括：跳过 **`__try`** 块、将 `longjmp` 控制传输到块的语句，并使堆栈展开堆栈，因为发生了异常处理。

> [!NOTE]
> Microsoft c + + 编译器支持两种形式的 `setjmp` 和 `longjmp` 语句。 快速版本会跳过终止处理，但更高效。 若要使用此版本，请包含文件 \<setjmp.h> 。 另一个版本支持上一段中所述的终止处理。 若要使用此版本，请包含文件 \<setjmpex.h> 。 快速版本的性能提升取决于硬件配置。

在执行任何其他代码前，操作系统将以适当的顺序执行所有终止处理程序，包括异常处理程序的主体。

当中断的原因是异常时，系统在决定要终止的内容前必须先执行一个或多个异常处理程序的筛选器部分。 事件的顺序如下：

1. 引发异常。

1. 系统查看活动异常处理程序的层次结构，并执行优先级最高的处理程序的筛选器。 这是最近安装的和最深层嵌套的异常处理程序，通过块和函数调用。

1. 如果此筛选器传递控制 (返回 0) ，则该过程将继续，直到找到不传递控制的筛选器。

1. 如果此筛选器返回-1，则执行将在引发异常的位置继续，而不会发生终止。

1. 如果筛选器返回 1，则发生以下事件：

   - 系统展开堆栈：清除引发异常的所有堆栈帧以及包含异常处理程序的堆栈帧。

   - 当堆栈展开时，堆栈上的所有终止处理程序都将执行。

   - 执行异常处理程序本身。

   - 控制权将交给此异常处理程序末尾后的代码行。

## <a name="see-also"></a>请参阅

[编写终止处理程序](../cpp/writing-a-termination-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
