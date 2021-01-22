---
description: 了解详细信息：延迟加载通知挂钩
title: 通知挂钩
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, notification hooks
ms.openlocfilehash: 401ae9099afcf00dc280bb4f9e5f7016a4cbc640
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667533"
---
# <a name="notification-hooks"></a>通知挂钩

在帮助程序例程中执行以下操作之前，将调用延迟加载通知挂钩：

- 系统将检查库的存储句柄，以查看其是否已加载。

- `LoadLibrary` 调用以尝试加载 DLL。

- `GetProcAddress` 调用以尝试获取过程的地址。

- 返回延迟导入加载 thunk。

通知挂钩已启用：

- 通过提供已初始化的指针的新定义， `__pfnDliNotifyHook2` 使其指向接收通知的自己的函数。

   \- 或 -

- 在对 `__pfnDliNotifyHook2` 程序进行延迟加载的任何调用之前，将指针设置为挂钩函数。

如果通知为 `dliStartProcessing` ，则挂钩函数可以返回：

- `NULL`

   默认 helper 处理 DLL 的加载。 仅出于信息目的而调用是非常有用的。

- 函数指针

   绕过默认的延迟负载处理。 它允许你提供自己的负载处理程序。

如果通知为 `dliNotePreLoadLibrary` ，则挂钩函数可以返回：

- 如果只需要信息性通知，则为0。

- `HMODULE`加载的 dll 的（如果它加载了 dll 本身）。

如果通知为 `dliNotePreGetProcAddress` ，则挂钩函数可以返回：

- 如果只需要信息性通知，则为0。

- 导入函数的地址（如果挂钩函数获取地址本身）。

如果通知为 `dliNoteEndProcessing` ，则忽略挂钩函数的返回值。

如果此指针初始化 (非零) ，延迟加载帮助器将在执行过程中的某些通知点调用函数。 函数指针具有以下定义：

```C
// The "notify hook" gets called for every call to the
// delay load helper.  This allows a user to hook every call and
// skip the delay load helper entirely.
//
// dliNotify == {
//  dliStartProcessing |
//  dliNotePreLoadLibrary  |
//  dliNotePreGetProc |
//  dliNoteEndProcessing}
//  on this call.
//
ExternC
PfnDliHook   __pfnDliNotifyHook2;

// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

通知会将结构中的传递 `DelayLoadInfo` 给挂钩函数以及通知值。 此数据与 "延迟加载帮助程序" 例程使用的数据相同。 通知值将是在 [结构和常量定义](structure-and-constant-definitions.md)中定义的值之一。

## <a name="see-also"></a>另请参阅

[错误处理和通知](error-handling-and-notification.md)
