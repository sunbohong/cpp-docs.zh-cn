---
title: 错误处理和通知
description: 了解更多： DLL 延迟加载错误处理和通知
ms.date: 01/19/2021
helpviewer_keywords:
- error handling, and notification
ms.openlocfilehash: a0161814a07bd5bbedbaa6d13c7c32cd3aeab559
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666948"
---
# <a name="error-handling-and-notification"></a>错误处理和通知

如果程序使用延迟加载的 Dll，它必须能够可靠地处理错误，因为在程序运行期间发生的失败将导致未经处理的异常。 故障处理由两部分组成：通过挂钩恢复，并通过异常进行报告。

有关 DLL 延迟加载错误处理和通知的详细信息，请参阅 [了解 helper 函数](understanding-the-helper-function.md)。

有关挂钩函数的详细信息，请参阅 [结构和常量定义](structure-and-constant-definitions.md)。

## <a name="recovery-through-a-hook"></a>通过挂钩恢复

你的代码可能需要在出现故障时恢复，或者需要提供备用库或例程。 可以向 helper 函数提供挂钩，该函数可提供备用代码或解决该问题。 挂钩例程需要返回合适的值，以便处理可以继续 (`HINSTANCE` 或 `FARPROC`) 。 或者，它可以返回0以指示应引发异常。 它还可能会引发自己的异常或 `longjmp` 超出挂钩。 存在通知挂钩和失败挂钩。

## <a name="reporting-via-an-exception"></a>通过异常报告

如果处理错误所需的全部操作都是中止过程，则只要用户代码可以处理异常，就不需要挂钩。

以下文章介绍了错误处理和通知：

- [通知挂钩](notification-hooks.md)

- [失败挂钩](failure-hooks.md)

- [DLL 延迟加载异常代码](exceptions-c-cpp.md)

## <a name="see-also"></a>另请参阅

[链接器的延迟加载 DLL 支持](linker-support-for-delay-loaded-dlls.md)
