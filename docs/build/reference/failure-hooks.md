---
description: 了解详细信息：延迟加载失败挂钩
title: 失败挂钩
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.openlocfilehash: 46cec6c66169ebe589bb5f0c912b2d8239e69da1
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667173"
---
# <a name="failure-hooks"></a>失败挂钩

启用失败挂钩的方式与 [通知挂钩](notification-hooks.md)相同。 挂钩例程需要返回合适的值，以便处理可以继续 (`HINSTANCE` 或 `FARPROC`) ，或为0以指示应引发异常。

引用用户定义函数的指针变量是：

```C
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

**`DelayLoadInfo`** 结构包含正确报告错误所需的所有相关数据，其中包括中的值 `GetLastError` 。

如果通知为 **`dliFailLoadLib`** ，则挂钩函数可以返回：

- 如果无法处理失败，则为0。

- `HMODULE`如果故障挂接修复了问题并加载了库本身，则为。

如果通知为 **`dliFailGetProc`** ，则挂钩函数可以返回：

- 如果无法处理失败，则为0。

- 有效的过程地址 (导入函数地址) （如果失败挂钩已成功获取地址本身）。

## <a name="see-also"></a>另请参阅

[错误处理和通知](error-handling-and-notification.md)
