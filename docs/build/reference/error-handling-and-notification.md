---
description: 了解详细信息：错误处理和通知
title: 错误处理和通知
ms.date: 11/04/2016
helpviewer_keywords:
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
ms.openlocfilehash: 234d50d0b4a7e8b81874d1926ac056f8cba23376
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200983"
---
# <a name="error-handling-and-notification"></a>错误处理和通知

有关错误处理和通知的详细信息，请参阅 [了解 Helper 函数](understanding-the-helper-function.md)。

有关挂钩函数的详细信息，请参阅 [结构和常量定义](structure-and-constant-definitions.md)。

如果程序使用延迟加载的 Dll，它必须稳定地处理错误，因为在程序运行期间发生的故障将导致未经处理的异常。 故障处理包括两个部分：

通过挂钩进行恢复。
如果你的代码需要在失败时恢复或提供备用库和/或例程，则可以向 helper 函数提供一个可以提供或纠正该情况的挂钩。 挂钩例程需要返回合适的值，以便处理可以继续 (HINSTANCE 或 FARPROC) 或0，以指示应引发异常。 它还可能会引发自己的异常，或 **longjmp** 出挂钩。 存在通知挂钩和失败挂钩。

通过异常进行报告。
如果处理错误所需的全部操作都是中止过程，只要用户代码可以处理异常，就不需要挂钩。

以下主题讨论错误处理和通知：

- [通知挂钩](notification-hooks.md)

- [失败挂钩](failure-hooks.md)

- [异常](exceptions-c-cpp.md)

## <a name="see-also"></a>请参阅

[Delay-Loaded Dll 的链接器支持](linker-support-for-delay-loaded-dlls.md)
