---
description: 了解详细信息：编写终止处理程序
title: 编写终止处理程序
ms.date: 11/04/2016
helpviewer_keywords:
- structured exception handling [C++], termination handlers
- exceptions [C++], terminating
- termination handlers [C++], writing
- handlers [C++]
- handlers [C++], termination
- termination handlers
- exception handling [C++], termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 52aa1f8f-f8dd-44b8-be94-5e2fc88d44fb
ms.openlocfilehash: a203cab7d61be66c5fe919aefe1895aa0928c5d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302980"
---
# <a name="writing-a-termination-handler"></a>编写终止处理程序

与异常处理程序不同，无论代码的受保护块是否已正常终止，终止处理程序总是会执行。 终止处理程序的唯一用途应该是确保无论代码的节如何完成执行，内存、句柄和文件等资源都能正确关闭。

终止处理程序使用 try-finally 语句。

## <a name="what-do-you-want-to-know-more-about"></a>你想进一步了解什么？

- [try-finally 语句](../cpp/try-finally-statement.md)

- [清理资源](../cpp/cleaning-up-resources.md)

- [异常处理的操作的计时](../cpp/timing-of-exception-handling-a-summary.md)

- [对于终止处理程序的限制](../cpp/restrictions-on-termination-handlers.md)

## <a name="see-also"></a>请参阅

[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
