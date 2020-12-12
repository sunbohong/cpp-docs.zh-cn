---
description: 详细了解：通知挂钩
title: 通知挂钩
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, notification hooks
ms.assetid: e9c291ed-2f2d-4319-a171-09800625256f
ms.openlocfilehash: 716d2b31faa71c77ec436662ce00368d15afc4b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209745"
---
# <a name="notification-hooks"></a>通知挂钩

在帮助程序例程中执行以下操作之前，将调用通知挂钩：

- 系统将检查库的存储句柄，以查看其是否已加载。

- 调用 **LoadLibrary** 来尝试加载 DLL。

- 调用了 **GetProcAddress** 来尝试获取过程的地址。

- 返回延迟导入加载 thunk。

通知挂钩已启用：

- 通过提供新的指针定义 **__pfnDliNotifyHook2** 初始化为指向你自己的接收通知的函数。

   \- 或 -

- 通过将指针设置 **__pfnDliNotifyHook2** 到挂钩函数，然后再调用对该程序延迟加载的 DLL。

如果通知是 **dliStartProcessing** 的，则挂钩函数可以返回：

- Null

   默认 helper 处理 DLL 的加载。 这对于只是为了提供信息而被调用非常有用。

- 函数指针

   绕过默认的延迟负载处理。 这允许你提供自己的负载处理程序。

如果通知是 **dliNotePreLoadLibrary** 的，则挂钩函数可以返回：

- 如果只需要信息性通知，则为0。

- 加载的 DLL 的 HMODULE （如果它加载了 DLL 本身）。

如果通知是 **dliNotePreGetProcAddress** 的，则挂钩函数可以返回：

- 如果只需要信息性通知，则为0。

- 导入函数的地址（如果挂钩函数获取地址本身）。

如果通知为 **dliNoteEndProcessing**，则忽略挂钩函数的返回值。

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

通知将在 **DelayLoadInfo** 结构中传递到挂钩函数以及通知值。 此数据与 "延迟加载帮助程序" 例程使用的数据相同。 通知值将是在 [结构和常量定义](structure-and-constant-definitions.md)中定义的值之一。

## <a name="see-also"></a>请参阅

[错误处理和通知](error-handling-and-notification.md)
