---
title: 对于终止处理程序的限制
description: 结构化异常处理终止处理程序的限制。
ms.date: 08/24/2020
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
ms.openlocfilehash: 60fdb4c2a105f2fce4a32f475563a04f8e7bfaf9
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898270"
---
# <a name="restrictions-on-termination-handlers"></a>对于终止处理程序的限制

不能使用 **`goto`** 语句跳转到 **`__try`** 语句块或 **`__finally`** 语句块。 相反，您必须通过常规控制流进入此语句块。 但 (可以跳出 **`__try`** 语句块。此外，还不能在块中嵌套异常处理程序或终止处理程序 ) 。 **`__finally`**

终止处理程序中允许的某些类型的代码会生成有问题的结果，因此，您应该谨慎使用。 一种语句是跳出 **`goto`** **`__finally`** 语句块。 如果块作为正常终止的一部分执行，则不会发生任何异常。 但如果系统正在展开堆栈，则展开将停止。 然后，当前函数会获得控制，就好像没有异常终止一样。

**`return`** 语句块内的 **`__finally`** 语句大致相同。 控件返回到包含终止处理程序的函数的直接调用方。 如果系统正在展开堆栈，则此进程将暂停。 然后，该程序将继续执行，就像未引发任何异常一样。

## <a name="see-also"></a>请参阅

[编写终止处理程序](../cpp/writing-a-termination-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
